# Python Package Cookiecutter Template

A cookiecutter template to create Python packages. It's tailored for those working in Azure DevOps with Azure Pipelines
and includes tools for testing, linting, documentation, versioning and publishing.

## Usage
Install [cookiecutter](https://cookiecutter.readthedocs.io/en/stable/installation.html) and then run:

```shell
cookiecutter https://github.com/tspanos/pythonPackageCookiecutter
```

## Features

- Python package setup with `src` layout.
- Azure Pipelines configuration for continuous integration and delivery.
- PyTest for testing
- Ruff for linting Python code.
- MkDocs for project documentation.

## Layout

An example project using this template would have the following structure:

- `src/`: Contains your Python package source code.
- `tests/`: Tests for your package.
- `docs/`: MkDocs documentation source files.
- `azure-pipelines.yml`: Configuration for Azure Pipelines.
- `pyproject.toml`: Defines project metadata and dependencies.

```
<project_name>/
├── .gitignore
├── azure-pipelines.yml
├── LICENSE.txt
├── mkdocs.yml
├── pyproject.toml
├── README.md
├── docs/
│   ├── index.md
│   └── installation.md
└── src/
|   └── <package_name>/
|       └── __init__.py
└── tests/
    └── tests.py
```

## Azure Pipelines

The `azure-pipelines.yml` includes several features:

- **Linting**: Ruff is used to lint the Python code.
- **Testing**: PyTest runs tests, test coverage is calculated and the results are published to Azure DevOps
- **Versioning**: Automatic versioning is handled by GitVersion.
- **Building**: Python packages are built into distributions.
- **Tagging**: Successful builds are tagged to the repository with the version number.
- **Publishing**: Built packages are submitted to an Azure Feed.

### Setup Requirements

- An Azure DevOps account and an Azure Pipeline setup.
- A Git Tools extension for Azure
  DevOps ([Git Tools](https://marketplace.visualstudio.com/items?itemName=gittools.gittools)).
- Azure Artifacts feed for publishing packages.
- Appropriate permissions for
  the ([build service account to interact with the Azure feed](https://stackoverflow.com/questions/58780741/azure-devops-user-lacks-permission-to-complete-this-action-you-need-to-have-a)).
- Appropriate permissions for
  the ([build service account to write to the repo](https://learn.microsoft.com/en-us/azure/devops/pipelines/scripts/git-commands?view=azure-devops&tabs=yaml)).
