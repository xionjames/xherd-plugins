# xherd-plugins

External plugins for [xherd](https://github.com/xionjames/xherd). One folder per plugin under `plugins/`; the folder name equals the manifest `name`.

| Plugin | Kind | Does |
|---|---|---|
| [`flutter`](plugins/flutter) | toolchain | Flutter SDK versions through `fvm`, from a `.flutter-version` file |

## Install

```sh
xherd plugin install https://github.com/xionjames/xherd-plugins --path plugins/flutter
```

Pin a release with a ref (`--ref flutter-v0.1.0`) instead of following `HEAD`. Restart xherd afterwards (`xherd daemon restart`).

Plugins run with the rights of the agents' user: read a plugin's commands in the preview before confirming.

## Rules for plugins here

- No `build` step: everything a plugin runs is committed, with the executable bit set.
- No symlinks.
- Bump the manifest `version` on every change.
