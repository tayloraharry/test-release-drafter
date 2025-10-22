# test-release-drafter

A proof-of-concept for using GitHub Release Drafter to automatically organize release notes into categories.

## Overview

This repository demonstrates how to use [Release Drafter](https://github.com/release-drafter/release-drafter) to automatically generate organized release notes from pull requests. Release notes are automatically categorized based on PR labels.

## Categories

Release notes are organized into the following categories:

- 🚀 **Features** - New features and enhancements (labels: `feature`, `enhancement`)
- 🐛 **Bug Fixes** - Bug fixes and corrections (labels: `bug`, `fix`)
- 🔧 **Tech Debt** - Technical debt, refactoring, and chores (labels: `tech-debt`, `refactor`, `chore`)
- 📝 **Documentation** - Documentation updates (labels: `documentation`, `docs`)

## How It Works

1. When a PR is opened, reopened, or updated, the Release Drafter workflow runs
2. When changes are pushed to the `main` branch, the workflow updates the draft release
3. PRs are automatically categorized based on their labels
4. The draft release is continuously updated with the latest changes

## Usage

### Labeling Pull Requests

To ensure your PRs appear in the correct category, add one of these labels:

- **Features**: `feature` or `enhancement`
- **Bug Fixes**: `bug` or `fix`
- **Tech Debt**: `tech-debt`, `refactor`, or `chore`
- **Documentation**: `documentation` or `docs`

### Version Control

You can also add version labels to control semantic versioning:

- `major` - For breaking changes (v1.0.0 → v2.0.0)
- `minor` - For new features (v1.0.0 → v1.1.0)
- `patch` - For bug fixes (v1.0.0 → v1.0.1, default)

### Viewing Draft Releases

1. Go to the repository's [Releases page](../../releases)
2. Click on the draft release to see the automatically generated release notes
3. When ready to publish, edit the draft and click "Publish release"

## Configuration Files

- `.github/release-drafter.yml` - Release Drafter configuration
- `.github/workflows/release-drafter.yml` - GitHub Actions workflow

## Example Release Notes

```markdown
## Changes

### 🚀 Features
- Add user authentication @username (#123)
- Implement dark mode @username (#124)

### 🐛 Bug Fixes
- Fix login redirect issue @username (#125)
- Resolve memory leak @username (#126)

### 🔧 Tech Debt
- Refactor database connection pool @username (#127)
- Update dependencies @username (#128)

### 📝 Documentation
- Update API documentation @username (#129)
```