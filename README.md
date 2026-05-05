# ghostty config

My personal [Ghostty](https://ghostty.org) configuration. Catppuccin Mocha tabs, transparent + blurred window, vim-style splits, JetBrainsMono Nerd Font.

## Install

```bash
git clone git@github.com:pyyupsk/ghostty.git ~/.config/ghostty
```

Reload an open Ghostty window with `ctrl+shift+,`, or open a new one.

## Theme line — what `?"..."` means

The first line of `config`:

```
config-file = ?"~/.config/omarchy/current/theme/ghostty.conf"
```

- `config-file = path` — Ghostty include directive that imports another config file.
- `?"..."` — the leading `?` means **optional**. Ghostty silently skips the include if the file does not exist (no error).
- `~/.config/omarchy/current/theme/ghostty.conf` is a symlink maintained by [Omarchy](https://omarchy.org) that points at the active system theme. As I switch Omarchy themes, the colors my terminal inherits change automatically.

### If you don't use Omarchy

That include resolves to nothing on your system, so Ghostty falls back to its default theme. To pin a theme yourself, replace the first line with one of:

```
# pick from `ghostty +list-themes`
theme = Catppuccin Mocha
```

```
theme = dark:Catppuccin Mocha,light:Catppuccin Latte
```

Or remove the line entirely.

## Highlights

- Catppuccin Mocha tab styling via [`tab-style.css`](./tab-style.css) (`gtk-custom-css`)
- Auto-hide tab bar when only one tab (libadwaita top tabs)
- Transparent background + blur (`background-opacity = 0.85`, `background-blur-radius = 20`)
- NVIDIA + Hyprland fix: `async-backend = epoll`
- Per-surface cgroup isolation: `linux-cgroup = always`

## Keybinds

| Action              | Keys               |
| ------------------- | ------------------ |
| Vertical split      | `alt+v`            |
| Horizontal split    | `alt+h`            |
| Close split / tab   | `alt+w`            |
| Move between splits | `ctrl+alt+h/j/k/l` |
| New tab             | `alt+t`            |
| Prev / next tab     | `alt+,` / `alt+.`  |
| Jump to tab N       | `alt+1`..`alt+9`   |
| Paste               | `shift+insert`     |
| Copy                | `ctrl+insert`      |
| Reload config       | `ctrl+shift+,`     |

## Fonts

[JetBrainsMono Nerd Font Mono](https://www.nerdfonts.com/font-downloads). Install the Nerd Font variant or change `font-family` in `config`.
