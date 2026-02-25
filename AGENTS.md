# AGENTS.md

## Cursor Cloud specific instructions

### Project overview

This repo has two unrelated components:

1. **Agents Toolkit** (root) — Documentation, scripts, and configs for running AI coding agents in isolated environments (devcontainers, worktrees). No runnable application.
2. **Creator Vaults Demo** (`demo/`) — A single static HTML file (`index.html`) with no build step, no framework, and no runtime dependencies. Serves an audio-visual investigation into creator token pump-and-dump patterns.

### Running the demo

Serve the `demo/` directory on any port with a static HTTP server:

```sh
cd demo && python3 -m http.server 3000
```

Or using Node.js: `cd demo && npx serve -l 3000`

The `demo/serve.sh` script also autodetects an available server.

### Caveats

- **No test suite exists.** There are no automated tests, no test framework, and no CI.
- **No linter is configured.** There is no ESLint, Prettier, or similar tooling.
- **No build step.** The demo is a single self-contained HTML file.
- **External audio dependency:** The demo's `<audio>` tag loads from `https://assets.creatorvaults.fun/audio/...`, which may not resolve in sandboxed/offline environments. The UI still loads and functions (play/pause, scene transitions, keyboard shortcuts) — only the audio stream is missing.
- **No npm dependencies to install.** The root `package-lock.json` is an empty placeholder. The `demo/package.json` has no `dependencies` or `devDependencies`.
