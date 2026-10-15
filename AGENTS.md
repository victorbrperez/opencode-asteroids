# AGENTS.md

## Project shape
- This repo is a small browser game: a single HTML page (`index.html`) that loads `game.js` directly.
- There is no package manager, bundler, framework, or test runner.
- All gameplay logic, rendering, collision logic, and state live in `game.js`.

## Run it
- Open `index.html` directly in the browser for the simplest check.
- Or start a local static server from the repo root:
  - `npx serve .`
  - then open `http://localhost:3000`
- The canvas runs at `800x600` and expects the browser DOM to be available as in the static page.

## Editing rules
- Prefer changing `game.js` for gameplay behavior; use `index.html` only for canvas shell and script wiring.
- Keep the project dependency-free. Do not add bundlers, package manifests, frameworks, or build tooling unless the task explicitly requires it.
- The game uses edge wrapping (`wrap(...)` in `game.js`), fixed ship physics, and asteroid split logic. Respect that behavior when changing gameplay.

## Verification
- Manual browser validation is the expected workflow: refresh the page and test controls (`Left/Right`, `Up`, `Space`).
- When changing collisions, score, asteroid splitting, or the ship loop, verify the behavior in `game.js` directly; there are no automated tests or CI checks to run.

## High-signal facts
- The app is intentionally static HTML/JS, not a Node app.
- `README.md` is the best source for run instructions and game controls.
- If a task seems to require a build pipeline, package install, or test suite, it is likely not a repo-native workflow; confirm before adding one.
