# MapBasic WebGIS

Minimal WebGIS powered by the Long Ngo Basemap CDN SDK and a canonical PMTiles archive.

## Live architecture

```text
index.html
  └─ LongNgoBasemap SDK (jsDelivr)
       └─ ./basemap.pmtiles (same-origin on GitHub Pages)
```

The site embeds:

```html
<script
  src="https://cdn.jsdelivr.net/gh/xulytiengviet/basemap@v1.2.0/sdk/basemap.min.js"
  data-target="map"
  data-archive="./basemap.pmtiles">
</script>
```

`basemap.pmtiles` is not committed to this repository. GitHub Actions downloads the verified artifact from the `xulytiengviet/basemap` v1.2.0 release during Pages deployment.

Canonical PMTiles:

- Size: `117829388` bytes
- SHA-256: `ff62a0549c722905ec30538fd4336bc93960e9a593c0eabe99600bc40ecbe77c`
- PMTiles v3 raster PNG
- Zoom 3–12

## GitHub Pages

Repository administrators should set **Settings → Pages → Build and deployment → Source → GitHub Actions** once. The workflow `.github/workflows/deploy-pages.yml` then publishes the complete site automatically.

Expected URL:

```text
https://xulytiengviet.github.io/mapbasic/
```
