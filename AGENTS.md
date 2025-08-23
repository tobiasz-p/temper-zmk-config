# Agent Guidelines for Temper ZMK Config

## Build Commands
- Build firmware: GitHub Actions automatically triggered on push/PR (uses `zmkfirmware/zmk/.github/workflows/build-user-config.yml`)
- Update keymap image: GitHub Actions workflow `doc.yml` triggers on keymap changes
- No local build/test commands - this is a ZMK firmware configuration repository

## File Structure
- Main keymap: `boards/shields/temper/temper.keymap`
- Shield configs: `boards/shields/temper/*.conf`, `*.overlay`, `*.dtsi`
- Build config: `build.yaml` (defines board/shield combinations)
- West config: `config/west.yml` (ZMK dependency management)

## Code Style Guidelines
- Use C-style comments `/* */` for license headers, `//` for inline comments
- Indent with 4 spaces, align code blocks consistently with existing style
- Define layer constants with `#define` (e.g., `#define DEFAULT 0`)
- Use descriptive behavior names with underscores (e.g., `bspc_del`, `smart_shft`)
- Follow ZMK devicetree syntax for behaviors and keymaps
- Maintain visual ASCII art alignment in keymap bindings for readability
- Use `&trans` for transparent keys, specific keycodes for functionality
- Group related behaviors in the behaviors section before keymap definition