# AGENTS.md

## Project overview

This repository (`reitowo/reitowo`) is a **GitHub profile README** repository. It contains a single file, `Readme.md`, which GitHub renders on the owner's profile page.

There is no application, backend, frontend, test suite, or package manager in this repo.

## Development workflow

1. Edit `Readme.md` (Markdown with optional inline HTML, common for profile READMEs).
2. Commit and push to `main` (or open a PR first).
3. GitHub updates the profile page after the change lands on the default branch.

## Validation

Optional markdown lint (expect style warnings for inline HTML and line length):

```bash
npx --yes markdownlint-cli Readme.md
```

Quick content sanity check:

```bash
python3 -c "
from pathlib import Path
text = Path('Readme.md').read_text()
assert 'reito.fun' in text
print('README validation OK')
"
```

## Cursor Cloud specific instructions

- **No install step**: There are no `package.json`, lockfiles, Docker, or CI configs. The VM update script is a no-op.
- **No services to start**: Nothing listens on a port. Do not run `npm dev`, `docker compose up`, or similar.
- **No lint/test/build scripts**: There is no Makefile or npm scripts. Use optional `markdownlint-cli` via `npx` if you need markdown checks.
- **Profile README conventions**: `Readme.md` intentionally uses centered HTML (`<div align="center">`) and badges; markdownlint will report MD033/MD041/MD013 warnings — that is expected and not a blocker for GitHub rendering.
- **Related projects**: Application code linked from the README (e.g. on [reito.fun](https://reito.fun) or [github.com/reitovo](https://github.com/reitovo)) lives in other repositories, not here.
