<div align="center">

<!-- Replace with your actual preview GIF -->
<img src="https://i.pinimg.com/originals/5c/84/56/5c8456fe235b39acf9b6cf970261d29b.gif" alt="Grid Studio Preview" width="720">

<br><br>

# Grid Studio — Dota 2 Grid Toolkit

**All-in-one editor for Dota 2 hero grids — heroes, symbol drawing & image conversion on a single canvas.**

[![License](https://img.shields.io/badge/license-MIT-white?style=flat-square&labelColor=0a0a0a&color=1a1a1a)](LICENSE)
[![Offline](https://img.shields.io/badge/offline-100%25-white?style=flat-square&labelColor=0a0a0a&color=1a1a1a)](#privacy)
[![Dependencies](https://img.shields.io/badge/deps-react%20%2B%20vite-white?style=flat-square&labelColor=0a0a0a&color=1a1a1a)](#setup)
[![JSON](https://img.shields.io/badge/format-Dota%20v3-white?style=flat-square&labelColor=0a0a0a&color=1a1a1a)](#two-save-formats)

<br>

[Live Demo](https://xokeza.github.io/dota2-grid-toolkit/) · [Report Bug](https://github.com/xokeza/dota2-grid-toolkit/issues) · [Feature Request](https://github.com/xokeza/dota2-grid-toolkit/issues)

</div>

---

## ⚡ Setup

> Requires **Node.js 22.19+**

```bash
git clone https://github.com/xokeza/dota2-grid-toolkit.git
cd dota2-grid-toolkit
npm ci
npm run dev
```

Open [localhost:4173](http://127.0.0.1:4173). This is a modular Vite build — `file://` won't work.

```bash
npm run build    # → dist/
npm run preview  # serve the built version
```

---

## 🎯 What It Does

React + Vite studio that combines three legacy tools into **one unified workspace** with shared undo/redo, layers, and a single document.

### Heroes
- 127 heroes with search, attribute filters & original game icons
- Vertical game portraits with Dota-accurate proportions
- Click "+" after the last hero to open the picker dialog

### Drawing
- Pencil, smart brush (`- | / \` auto-orientation), shapes, fill, frames, eraser
- Symbol library with 18+ categories
- Sequence, random or gradient brush modes with adjustable density
- Mirror X/Y symmetry

### ASCII from Image
- Built-in Canny edge detector with Zhang-Suen thinning
- Live preview with all parameters: blur, threshold, density, shading
- One click to add result as a separate layer

### Layers & Editing
- Background / Heroes / Decor + separate layer per image or ASCII
- Rename, hide, lock, duplicate, delete layers (with undo)
- Lasso selection, proportional resize, rotation, alignment
- Strings auto-merge within layers preserving exact spacing

### Interface
- SF Pro Display web font, smooth animations, reduced-motion support
- Responsive: panels collapse on narrow screens
- Live symbol counter, grid & snap controls, zoom

---

## 🔄 Workflow

1. **Import** your `hero_grid_config.json` → switch grids in the left panel
2. **Add heroes** via the picker dialog
3. **Draw** symbols, frames, and decoration on the Drawing tab
4. **Convert images** to ASCII on the ASCII tab
5. **Export** → all grids in one Dota-ready JSON

---

## 📦 Two Save Formats

| Format | Purpose |
|---|---|
| `hero_grid_config.json` | For Dota 2. Visible objects → v3 categories. |
| `*.gridstudio.json` | Project file. Preserves layers, locks, drafts. |

---

## ⌨️ Hotkeys

| Keys | Action |
|---|---|
| `V` / `B` / `T` / `R` / `E` / `L` | Select / brush / text / rect / eraser / lasso |
| `Space` + drag | Pan canvas |
| `F` | Focus mode (large canvas) |
| `G` / `P` | Grid / preview |
| `+` / `-` / `0` | Zoom in / out / fit |
| `Ctrl+Z` / `Ctrl+Shift+Z` | Undo / redo |
| `Ctrl+S` / `Ctrl+O` | Save project / open file |
| `Delete` / `Esc` | Delete / deselect |

---

## 🎮 Install Grid in Dota 2

1. Close Dota 2
2. Find `Steam/userdata/<account_id>/570/remote/cfg/hero_grid_config.json`
3. Back it up, import into Grid Studio, edit, export
4. Replace the file, launch Dota

---

## 📁 Project Structure

```
dota2-grid-toolkit/
├── index.html              # SPA entry
├── src/                    # React components (JSX)
├── scripts/                # Core logic modules (MJS)
├── styles/                 # CSS (studio, site, drawing, focus, etc.)
├── assets/
│   ├── heroes/             # Hero mini icons (PNG)
│   ├── portraits/          # Hero portraits (JPG)
│   └── favicon.svg
├── data/                   # symbols, heroes, ascii-arts JSON
├── presets/                # Line-art converter presets
├── tools/                  # Legacy standalone HTML tools
├── tests/                  # Node.js test suite
├── docs/                   # Architecture, QA, design docs
├── vite.config.mjs
└── package.json
```

---

## 🛠 Legacy Tools

The original standalone HTML tools are preserved and still work:

- [Line-Art Converter](tools/lineart-converter.html) — image → ASCII symbols via Canny
- [Pixel ASCII Editor](tools/pixel-ascii-editor.html) — manual symbol drawing
- [Hero Grid Editor](tools/hero-grid-editor.html) — category management

---

## 🧪 Development

```bash
npm run check   # syntax check all modules
npm test        # run test suite
```

Tests cover: symbol library sync, import/export, multi-grid files, undo history, ASCII layers, proportional resize, rotation, game geometry, Unicode counting, converter, and local portraits.

---

## 🔒 Privacy

- No analytics, accounts, or file uploads
- SF Pro Display loaded from CDN (falls back to system font)
- All JSON and images processed locally in browser
- Source code: [MIT](LICENSE)

---

<div align="center">

**[xokeza](https://github.com/xokeza)**

</div>
