# Vendored browser map libraries

These files are checked in so the beta build has no runtime dependency on a
public JavaScript CDN. `apps/game/web/index.html` loads them directly.

| File | Upstream project | Version | Licence |
|---|---|---|---|
| `maplibre-gl.js` | MapLibre GL JS | 5.24.0 | BSD-3-Clause |
| `maplibre-gl.css` | MapLibre GL JS | 5.24.0 | BSD-3-Clause |
| `pmtiles.js` | PMTiles | 4.5.0 | BSD-3-Clause |

The files are the unmodified upstream dist builds. The Dart `maplibre`
package expects the JS globals `maplibregl` and `pmtiles`.

## Updating

1. Download the new dist files from the matching upstream release into this
   directory (MapLibre GL JS: `dist/maplibre-gl.js` and `dist/maplibre-gl.css`;
   PMTiles: `dist/pmtiles.js`).
2. Update the version table above and the comment in `apps/game/web/index.html`.
3. Rebuild with `./tools/build_web.sh` and confirm the page and vendor files load
   from the local build, not from a remote script host.
