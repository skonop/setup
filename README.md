# Python Project Template

A template for Python projects with development container support and modern dependency management using `uv`.

## Getting Started

### 1. Create Your Project

Clone this template and initialize your new project:
```bash
# Clone the template
git clone https://github.com/skonop/setup my-project
cd my-project

# Initialize new git repository
make init-git
```

### 2. Check Development Environment

Verify your local environment has the required tools:
```bash
make check-env
```

This checks for:
- Python version
- `uv` package manager presence

### 3. Development Options

#### Option A: Using VS Code Dev Container (Recommended)
1. Install VS Code and the "Dev Containers" extension
2. Open the project folder in VS Code
3. When prompted, click "Reopen in Container" or run:
   - Command Palette (Cmd/Ctrl + Shift + P)
   - "Dev Containers: Rebuild and Reopen in Container"

The container will:
- Use Python 3.11
- Install `uv` package manager
- Install dependencies from `pyproject.toml`

#### Option B: Local Development
```bash
make local-dev
```

### 4. Project Configuration

1. Update `pyproject.toml`:
   - Set your project name, version, and description
   - Add your dependencies
   - Configure development tools

2. Update container settings (optional):
   - Edit `.devcontainer/devcontainer.json` for container customization
   - Add additional VS Code extensions or settings

## Project Structure

```
.
├── .devcontainer/          # Development container configuration
├── src/                    # Source code
│   ├── __init__.py
│   └── __main__.py        # Entry point
├── tests/                  # Test files
├── Makefile               # Development commands
└── pyproject.toml         # Project metadata and dependencies
```

## Available Make Commands

- `make help` - Show available commands
- `make init-git` - Initialize new git repository
- `make devcontainer` - Show instructions for dev container setup
- `make local-dev` - Run the project locally
- `make check-env` - Verify development environment

## Environment Variables

This template uses `prettyconf` for environment variable management. Create a `.env` file in your project root for local configuration.

## Testing the Template

Run the template tests to verify everything is working:
```bash
make test
```

This will:
1. Create a temporary test directory
2. Copy the template
3. Run through all main targets (`help`, `check-env`, `init-git`, `local-dev`)
4. Clean up the test directory
