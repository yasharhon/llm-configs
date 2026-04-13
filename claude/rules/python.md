---
paths:
  - "**/*.py"
---

## Python coding guidelines

### General principles
Good Python code is
- Clearly type hinted
- Based on stable underlying types
- Always documented
- Portable between environments

### Tooling
The base tooling stack for Python coding is:
- `uv` for project management and local running
- `ruff` for linting and formatting
- `ty` for type checking

Invoke the relevant /astral:<skill> for uv, ty, and ruff to ensure best practices are followed.

### Writing code

#### Structure and readability
- DO:
    - Always type hint code
    - Always write clear docstrings for each function
    - Use the Google docstring format
- DO NOT:
    - Use type and linting ignores. These are for when absolutely necessary, and require detailed and explicit explanation
    - Use mid-file imports. Imports are done at the start of a module - AND NOWHERE ELSE

#### Code organization
- DO:
    - Separate code into functions
    - Decompose the code into reusable functions
    - Split code into distinct modules, each having a well-defined and limited scope. To do this, identify reusable functions before writing code

#### Design practices
- DO:
    - Treat distinct types of exceptions differently
- DO NOT:
    - Use global variables
    - Structure data as dictionaries with arbitrary string keys
    - Insert default values if data is missing - unless specifications demand this explicitly. Otherwise, code that throws errors are good
    - Write long try-catch blocks. Exceptions should be caught as locally as possible
    - Catch the general `Exception`. Caught exceptions should be specific

#### Preferred libraries
- `pydantic` for data models with validation and JSON serialization needs
- `pydantic-settings` for application settings
- `pathlib` for managing file paths
- `argparse` for writing CLIs and taking CMD arguments