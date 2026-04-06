# 🗺️ Image to GeoJSON

Turn any image into georeferenced GeoJSON by placing control points on the image, assigning real‑world latitude and longitude coordinates, and exporting the result.

## Features

- Upload PNG, JPG, or WebP images directly in the browser.
- Click on the image to place **control points** with pixel‑position labels.
- Assign **latitude (‑90 to 90)** and **longitude (‑180 to 180)** for each point.
- Generate a GeoJSON with:
  - A `Polygon` feature for the image extent.
  - `Point` features for each control point, including:
    - `pixel_x_pct`, `pixel_y_pct`
    - `input_lat`, `input_lng`
    - `coordinates` in `[lng, lat]`
- Copy the GeoJSON to clipboard or download as `georeferenced.geojson`.

## Technical notes

- The app runs entirely in the browser; no server‑side processing.
- An **affine transform** is fitted to your `(px, py, lat, lng)` tuples to map image pixels to geographic coordinates.
- The resulting GeoJSON uses WGS84 (EPSG:4326) with `[lng, lat]` coordinates, suitable for use in QGIS, MapLibre, Leaflet, or any GeoJSON‑compatible tool.


## License

This project is released under the [MPL-2.0 License](https://choosealicense.com/licenses/mpl-2.0/).