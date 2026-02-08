# Changelog

## [Unreleased] - 2026-02-08

### Added
- Support for GNOME Shell 45, 46, 47, 48, and 49
- New `_notify()` helper using `MessageTray.Source` and `MessageTray.Notification` (replaces deprecated `Main.notify`)

### Fixed
- Fixed restore function using double slashes in file paths (`file:///` + absolute path)
- Fixed restore function using URL-encoded filenames instead of actual filenames

### Changed
- Migrated from legacy `imports.*` system to ESM (`import` / `export default`)
- Replaced `imports.gi.*` with `gi://` module imports
- Replaced `imports.ui.*` with `resource:///org/gnome/shell/ui/` imports
- Replaced `ByteArray.toString()` with `TextDecoder().decode()`
- Replaced deprecated `log()` / `log.error()` with `console.log()` / `console.error()`
- Replaced deprecated `add_actor()` / `add()` with `add_child()`
- Replaced `St.Align.START` with `Clutter.ActorAlign.START`
- Replaced `Clutter.Escape` with `Clutter.KEY_Escape`
- Replaced `constructor()` with `_init()` / `super._init()` in GObject classes
- Moved `InteractiveDialog` class before `TrashMenu` (fixes usage-before-declaration)
- Extension class now uses `export default class` extending `Extension`
- Fixed `_onOpenTrash()` to use `'trash:///'` literal instead of undefined `this.trashPath`
- Fixed typos: `openDirecoryCallback` -> `openDirectoryCallback`, `currentDirecoryChildren` -> `currentDirectoryChildren`
- Cleaned up commented-out code and trailing whitespace

### Removed
- Legacy `init()`, `enable()`, `disable()` top-level functions (replaced by Extension class)
- `_ornamentLabel.visible` workaround (no longer needed)
- Redundant `this.show()` call in `_onTrashChange()` (already setting `this.visible`)
