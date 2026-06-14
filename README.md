# python-project-template
A basic Python project template with pyproject.toml so I don't have to figure this out every time. Can implement as a cookiecutter template if using it often.

## Usage

1. Clone / copy the files needed.
2. Rename `python/myprojectpkg` to the package name you are using.
3. Adjust the pyproject.toml file in the following way:
  - Replace all instances of `myprojectpkg` with the package name you are using.
  - Change `[project]` section (author, description, license, ...)
  - Adjust tool configurations as needed
4. Change `LICENSE` file to match license in use.

## Provided environments

If you're using hatch, it provides the following environments and commands.

### test

Uses `pytest` and `coverage`.

* `hatch run test:run`: Run pytest without coverage.
* `hatch run test:cov`: Run pytest with coverage and report results.
    - This is a convenience that runs `test:cov-run`, `test:cov-report`, and `test:clean` in sequence.

### lint

Uses ruff for formatting and linting.

These can be used for checking (eg. in CI)

* `hatch run lint:format-check`
* `hatch run lint:lint`
* `hatch run lint:check`: runs both of the above in sequence
    - Note that in CI usually the first failure will cause the second command not to run.

These are the equivalent auto-fix commands:

* `hatch run lint:format`
* `hatch run lint:fix`
* `hatch run lint:fix-all`: runs both of the above in sequence

### type

* `hatch run type:check` runs mypy static type checking.
