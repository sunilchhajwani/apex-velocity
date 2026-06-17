# 🏎️ Apex Velocity — 3D Racing Game

A browser-based 3D racing game built with **Three.js** (WebGL). Single HTML file, no dependencies, runs instantly.

![Apex Velocity](https://img.shields.io/badge/Three.js-r128-green) ![No dependencies](https://img.shields.io/badge/dependencies-zero-blue) ![Single file](https://img.shields.io/badge/file-single%20HTML-orange)

## Features

- **3D car with driving physics** — acceleration, braking, reverse, steering, handbrake drifting
- **Closed-loop race track** — Catmull-Rom spline with barriers, lane markings, checkered start/finish line
- **Lap system** — 3 laps, current lap timer, best lap tracking, lap notifications
- **HUD** — speed gauge with bar, lap counter, lap timer, best lap display
- **Minimap** — real-time track map with car position and heading
- **Scenery** — trees, rocks, grass, sky with fog
- **Lighting & shadows** — directional sun with PCF soft shadows, hemisphere ambient
- **Particle effects** — dust particles when accelerating, drifting, or driving on grass
- **Engine sound** — Web Audio API procedural engine sound that scales with speed
- **Chase camera** — smooth follow camera that adjusts distance/height with speed
- **Off-track penalty** — car slows on grass and gets pushed back toward road

## Play

### Option 1: Open the file directly
```bash
# macOS
open index.html

# Linux
xdg-open index.html

# Windows
start index.html
```

### Option 2: Serve locally (recommended — avoids CORS issues)
```bash
# Python 3
python3 -m http.server 8765
# Then open http://localhost:8765 in your browser
```

## Controls

| Key | Action |
|-----|--------|
| **W** / ↑ | Accelerate |
| **S** / ↓ | Brake / Reverse |
| **A** / ← | Steer Left |
| **D** / → | Steer Right |
| **Space** | Handbrake (drift) |
| **R** | Reset car to start |

## How it works

- **Track**: Generated from a Catmull-Rom spline through 15 control points, extruded into a road mesh with canvas-textured asphalt and lane markings
- **Car**: Built from primitive Three.js geometries (boxes, cylinders, cones) — body, cabin, windshield, spoiler, headlights, taillights, 4 rotating wheels
- **Physics**: Custom arcade-style physics — speed/heading model with friction, steering proportional to speed, grip model for handbrake drifting
- **Lap detection**: Tracks car position along the curve (0→1 parameter), detects forward crossing of start/finish with halfway-point validation
- **Minimap**: Pre-computed track outline scaled to canvas, with car dot and heading vector

## Browser compatibility

| Browser | Status |
|---------|--------|
| Chrome / Edge | ✅ Full support |
| Firefox | ✅ Full support |
| Safari | ✅ Full support |
| Headless browsers | ⚠️ May lack WebGL — use a real browser |

## Tech stack

- **Three.js r128** (CDN, no install)
- **WebGL** for 3D rendering
- **Web Audio API** for engine sound
- **Canvas 2D** for minimap and road texture
- No build tools, no npm, no frameworks — just one HTML file

## License

MIT