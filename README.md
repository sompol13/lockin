# lockin

A tiny focus timer for the terminal. Start a session, get a nudge to ship, and a macOS notification when time is up.

```console
$ lockin
🎯 Locked in for 50 minutes — Many done beats one perfect.
$ lockin status
🔒 42m 10s left — One exception can become a habit.
```

## Install

```sh
brew install sompol13/tap/lockin
```

Requires macOS (uses `osascript` for notifications) and zsh (preinstalled on macOS).

## Usage

| Command | Description |
| --- | --- |
| `lockin [minutes]` | Start a session (default: 50 minutes) |
| `lockin status` | Show time left |
| `lockin stop` | End the session early |
| `lockin --version` | Print version |

Only one session runs at a time. State is kept in `$TMPDIR/lockin.state`.

## Releasing

1. Bump `VERSION` in `bin/lockin` and commit.
2. `git tag vX.Y.Z && git push --tags && gh release create vX.Y.Z --generate-notes`
3. In [sompol13/homebrew-tap](https://github.com/sompol13/homebrew-tap), update `url` and `sha256` in `Formula/lockin.rb`:
   `curl -sL https://github.com/sompol13/lockin/archive/refs/tags/vX.Y.Z.tar.gz | shasum -a 256`
4. `brew upgrade lockin`

## License

MIT
