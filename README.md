# Geospatial Analysis Toolkit

## 📌 Overview
This repository provides a comprehensive set of tools for geospatial analysis using Python. It includes modules for:
- **Thematic Analysis**: Extract and visualize patterns from spatial data.
- **Overlay Analysis**: Combine multiple geospatial datasets to derive new insights.
- **Geemap**: Utilize the power of Google Earth Engine (GEE) with Python for large-scale geospatial processing.
- **Interactive Maps**: Create dynamic and user-friendly visualizations for exploratory spatial data analysis.

---

## 🚀 Features
✅ Perform advanced **thematic mapping** with geospatial data.<br>
✅ Conduct **spatial overlay operations** to analyze relationships between layers.<br>
✅ Integrate **Google Earth Engine (GEE)** for cloud-based geospatial processing.<br>
✅ Generate **interactive maps** with `folium`, `geemap`, and `ipywidgets`.<br>
✅ Supports **GeoJSON, Shapefiles, and Raster** data formats.<br>
✅ Easily customizable and scalable for different geospatial applications.<br>

---

## 🛠 Installation
To use this toolkit, install the required dependencies:

```bash
pip install geopandas rasterio folium geemap shapely matplotlib
```

Ensure you have access to **Google Earth Engine** if you intend to use `geemap`.

---

## 📖 Usage
### 1️⃣ Thematic Analysis
```python
import geopandas as gpd
import matplotlib.pyplot as plt

# Load shapefile
data = gpd.read_file('data.shp')

# Plot thematic map
data.plot(column='population_density', cmap='coolwarm', legend=True)
plt.show()
```

### 2️⃣ Overlay Analysis
```python
from geopandas.tools import overlay

# Load two layers
layer1 = gpd.read_file('layer1.shp')
layer2 = gpd.read_file('layer2.shp')

# Perform overlay (intersection)
result = overlay(layer1, layer2, how='intersection')
result.plot()
plt.show()
```

### 3️⃣ Geemap (Google Earth Engine Integration)
```python
import geemap
import ee

# Authenticate and initialize GEE
ee.Initialize()

# Create map and add dataset
Map = geemap.Map()
dataset = ee.Image('USGS/SRTMGL1_003')
Map.addLayer(dataset, {'min': 0, 'max': 3000, 'palette': ['blue', 'green', 'yellow', 'red']}, 'Elevation')
Map
```

### 4️⃣ Interactive Maps
```python
import folium

# Create map centered on a location
m = folium.Map(location=[-7.250445, 112.768845], zoom_start=12)

# Add marker
folium.Marker([-7.250445, 112.768845], popup='Surabaya, Indonesia').add_to(m)

# Display map
m
```

---

## 📂 Project Structure
```
├── data/                 # Shapefiles and geospatial datasets
├── notebooks/            # Jupyter notebooks for examples
├── scripts/              # Python scripts for automated processing
├── README.md             # Project documentation
```

---

## 📌 Requirements
- Python 3.8+
- `geopandas`, `shapely`, `folium`, `rasterio`, `matplotlib`
- Google Earth Engine (optional for geemap module)

---

## 🤝 Contributing
Contributions are welcome! Feel free to submit issues and pull requests.

---

## ⭐ Acknowledgments
Special thanks to the open-source GIS community and contributors to `geopandas`, `geemap`, and `folium`.

