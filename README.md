# La Suite Numérique Buildpack

This is a custom Scalingo buildpack designed to build applications from La Suite Numérique. It handles applications with the following structure:

- `src/backend`: Django backend application
- `src/frontend`: Next.js frontend application

## How it works

This buildpack:

1. Detects if the application follows La Suite Numérique structure
2. Builds the Django backend using Scalingo's Python buildpack
3. Builds the Next.js frontend
4. Sets up the necessary routing and configuration

## Usage

Add this buildpack to your Scalingo application:

```bash
scalingo buildpacks-add https://github.com/[your-org]/lasuite-buildpack
```

Make sure your application has the following structure:
```
src/
  backend/
    requirements.txt
    manage.py
    ...
  frontend/
    package.json
    ...
```

## Configuration

The buildpack will automatically detect and use:
- Python requirements from `src/backend/requirements.txt`
- Node.js dependencies from `src/frontend/package.json` 