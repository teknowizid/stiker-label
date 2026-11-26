# Label Printer Studio

A Windows 11 Fluent-styled desktop application for designing and printing thermal sticker labels (`50.8mm x 31mm`, 203 DPI), built with Python (`CustomTkinter`), `Pillow`, and `pywin32`.

## Features

- **Windows 11 Fluent Design UI**:
  - Clean 3-panel studio layout (**Add & Layers**, **Interactive Canvas**, **Properties Inspector**) with **Light / Dark / System** theme switching and native Windows 11 titlebar styling.
- **Design Elements**:
  - **Multi-line Text & Emoji**: Add multi-line text (with emoji support), choose `Left` / `Center` / `Right` alignment, and **edit text inline on the canvas** by double-clicking.
  - **Images**: Add `.jpg`, `.png`, `.bmp`, or `.webp` images and resize proportionally using **corner handles directly on the canvas** or the scale slider (`10%–300%`).
  - **Shapes (`Box` & `Line`)**: Add border/filled boxes and lines with adjustable thickness (`1–20 px`), rotation, and canvas corner resizing.
- **Filterable Font Picker**:
  - Floating Windows-style font picker displaying clean system font names (`.ttf` / `.otf` from the Windows Registry) with instant keyword filtering.
- **Interactive Canvas & Precision Controls**:
  - Drag-and-drop positioning with **snap guide lines** (snaps to canvas center and other elements' edges/centers).
  - Zoom presets (`Fit`, `1x`, `1.5x`, `2x`) with automatic scrollbars when zoomed in.
  - Quick rotation (`0°`, `90°`, `180°`, `270°`), one-click centering (`Center H`, `Center V`, `Center`), layer z-order controls (`↑` / `↓`), duplicate (`Ctrl+D`), and arrow-key nudging (`Shift+Arrow` for `10 px`).
- **Undo / Redo & Unsaved Changes Protection**:
  - Up to 50 steps of **Undo / Redo** (`Ctrl+Z` / `Ctrl+Y`).
  - Window title `*` dirty indicator and save confirmation when closing or switching files.
- **File Menu, Autosave & Open Recent**:
  - Unified **`File`** dropdown menu (`New`, `Open`, `Open Recent` up to 10 persistent projects, `Save`, `Save As`, `Autosave` toggle, `Print`, `Exit`).
  - Repeated `Save` updates the active `.json` file directly without re-prompting, while the status bar shows the saved directory and filename.
  - **Autosave** (enabled by default) saves every change immediately to the active project file, or to a recovery draft in `%APPDATA%\LabelPrinterStudio\autosave_draft.json` before the first save.
- **Direct Windows Printing**:
  - Print directly to installed Windows printers with a printer list refresh button (`↻`) and copies stepper.

## Keyboard Shortcuts

| Shortcut | Action |
| :--- | :--- |
| `Ctrl+N` | New / Clear label |
| `Ctrl+O` | Open `.json` project |
| `Ctrl+S` | Save project |
| `Ctrl+Shift+S` | Save As |
| `Ctrl+P` | Print label |
| `Ctrl+Z` / `Ctrl+Y` | Undo / Redo |
| `Ctrl+D` | Duplicate selected element |
| `Delete` | Delete selected element |
| `Arrow Keys` / `Shift+Arrow` | Nudge selected element (`1 px` / `10 px`) |
| `Double-Click` (on text) | Edit text inline (`Enter` apply, `Shift+Enter` newline, `Esc` cancel) |

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/teknowizid/stiker-label.git
   cd stiker-label
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

Run the application:
```bash
python run.py
```
Or double-click `run.bat` on Windows to launch directly without building (automatically checks Python & dependencies).

### Running Tests

```bash
python -m pytest -v tests/test_parsing.py tests/verify_logic.py tests/verify_saveload.py tests/reproduction_rotation.py
```

### Building the Executable (Windows)

To create a standalone `.exe` file:
```bash
python build_exe.py
```
The executable will be located in the `dist/` folder.

## License
MIT
