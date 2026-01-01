# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal landing page for Drew Shahoud - a single-page static website with cyberpunk aesthetics.

## Architecture

This is a zero-dependency static site consisting of a single `index.html` file with:
- Embedded CSS (no external stylesheets)
- Embedded JavaScript (no build process or bundling)
- Canvas-based animated background using Simplex noise for topographic line generation
- Glitch effects triggered by user interactions (clicks, scroll attempts)

## Development

Open `index.html` directly in a browser - no server or build step required.

To serve locally with live reload, use any static file server:
```bash
python3 -m http.server 8000
# or
npx serve .
```

## Key Implementation Details

- **Simplex Noise**: Custom implementation (lines 290-366) generates the animated topographic background
- **Glitch System**: CSS animations combined with JS event handlers create RGB split, screen shake, scanlines, and static noise effects
- **Scroll Prevention**: Intentionally blocks scrolling and shows a popup when users attempt to scroll
- **Color State**: Background transitions to red (#dc3c3c) for 3 seconds when scroll is attempted
