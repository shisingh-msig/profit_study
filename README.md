# profit_study

## Overview
Lightweight study / exploration repository managed with Poetry.

## Prerequisites
- Python 3.11 – 3.13 installed (currently using 3.13)
- Poetry installed

Check versions:

```powershell
python --version
poetry --version
```

## Initial Setup
Clone repo and install dependencies (creates virtualenv automatically):

```powershell
git clone <your-fork-or-origin-url>
cd profit_study
poetry env use "C:\Users\Shiv.Singh\AppData\Local\Programs\Python\Python313\python.exe"  # adjust path if different
poetry install
```

## Project Structure
```
pyproject.toml        # Project + dependency metadata
src/profit_study/     # Package source
tests/                # Pytest tests
```

## Running the Package
Run the sample entrypoint (prints greeting):

```powershell
poetry run python -m profit_study.main
```

Or open an interactive shell in the venv:

```powershell
poetry shell
python -c "import profit_study, inspect; print(profit_study.main())"
exit
```

## Running Tests
```powershell
poetry run pytest
```

## Adding a Dependency
Runtime dependency example:
```powershell
poetry add requests
```

Dev-only dependency example:
```powershell
poetry add --group dev black
```

## Updating Dependencies
```powershell
poetry update
```

## Lock File Policy
Currently `.gitignore` excludes `poetry.lock`. If you want reproducible installs across machines, remove `poetry.lock` from `.gitignore` and commit it.

## Running a Script Pattern
Add a script entry under `[tool.poetry.scripts]` in `pyproject.toml`, e.g.:
```
[tool.poetry.scripts]
profit-study = "profit_study.main:main"
```
Then run:
```powershell
poetry run profit-study
```

## Troubleshooting
- If imports fail in tests, ensure `pythonpath = ["src"]` is present under `[tool.pytest.ini_options]` in `pyproject.toml`.
- To remove and recreate the virtualenv:
```powershell
poetry env remove python
poetry env use <path-to-python.exe>
poetry install
```

## Next Ideas
- Add Black + Ruff for formatting / linting
- Add pre-commit hooks
- Expand test coverage

---
Happy coding!