# mnc-vehicle-clustering

mnc-vehicle-clustering

## What it does

| Step | What it does |
|---|---|
| **Set Workflow Details** | Add information that will help to differentiate this workflow from another. |
| **Set Time Range** | Choose the period of time to analyze. |
| **Set Groupers** |  |
| **Basemap URLs** |  |
| **Connect to EarthRanger** |  |
| **Subject Group** | Get observations for a subject group from EarthRanger. |
| **Get Spatial Features Group** |  |
| **Process Relocations** |  |
| **Compute View State From Gdf** |  |
| **Spatial Feature Overlay** | Creates a GeoJSON layer definition based on the provided configuration. |
| **Create Meshgrid** | Create a grid from the provided area of interest. |
| **Projected Spatial** | Re-project a GeoDataFrame's geometries to the given CRS. |
| **Relocations To Trajectory** |  |
| **Overlay Meshgrid with Projected Spatial Layer** | Overlay two GeoDataFrames. |
| **Persist Trajectories** | Persist dataframe to a file or cloud storage object. |
| **Calculate Linear Time Density** |  |
| **Detect Vehicle Clusters Over Time** | Replay the whole period and find vehicle clusters at regular snapshots. |
| **Apply Color Map** | Adds a color column to the dataframe based on the categorical values in the specified column. |
| **Create Scatterplot Layer** | Creates a scatterplot layer definition based on the provided configuration. |
| **Group Cluster Episodes** | One row per crowding incident: when, where, how long and how many vehicles. |
| **Episode Vehicle Minutes** | One row per vehicle per crowding incident: when it was first and last seen in the cluster, and for how many minutes (snapshots present x `interval_minutes`). |
| **Convert Crs** | Re-project a GeoDataFrame's geometries to the given CRS. |
| **Persist Cluster Episodes** | Persist dataframe to a file or cloud storage object. |
| **Persist Vehicle Minutes** | Persist dataframe to a file or cloud storage object. |
| **LTD Layer** | Creates a GeoJSON layer definition based on the provided configuration. |
| **Draw Vehicle Table** | Creates an HTML table of the provided dataframe. |
| **Combine Deckgl Map Layers** | Combine static and grouped map layers into a render-ready list. |
| **Clustering Map** | Creates a map based on the provided layer definitions and configuration. |
| **Persist Vehicle Table** | Persist text to a file or cloud storage object. |
| **Persist Cluster Map** | Persist text to a file or cloud storage object. |
| **Create Table Widget Single View** | Create a table widget with a single view. |
| **Create Map Widget Single View** | Create a map widget with a single view. |
| **Gather Dashboard** |  |

## Requirements

- Access to a **EarthRanger** data source, set up as a connection

---

## 1. Load the Workflow

In the workflow runner, add a new template using this repository's URL. Once added, select
**mnc-vehicle-clustering** from the available templates list to load it.

---

## 2. Configure the Workflow

You'll be prompted to fill in the following parameters before running.

### Set Workflow Details

| Field | Description | Default |
|---|---|---|
| Workflow Name *(required)* |  | — |
| Workflow Description |  | `` |

### Set Time Range

| Field | Description | Default |
|---|---|---|
| Since *(required)* | The start time | — |
| Until *(required)* | The end time | — |
| Timezone |  | — |

### Basemap URLs

| Field | Description | Default |
|---|---|---|
|   | Select tile layers to use as base layers in map outputs. The first layer in the list will be the bottommost layer displayed. | `[{"url": "https://server.arcgisonline.com/ArcGIS/rest/ser…` |

### Connect to EarthRanger

| Field | Description | Default |
|---|---|---|
| Data source *(required)* | Select one of your configured data sources. | — |

### Subject Group

| Field | Description | Default |
|---|---|---|
| Subject Group Name *(required)* | ⚠️ The use of a group with mixed subtypes could lead to unexpected results | — |

---

## Developing

```bash
# recompile spec.yaml (first time: --install; after that: --update, which bumps VERSION.yaml)
./dev/recompile.sh --update

# run the test cases in test-cases.yaml
pixi run --manifest-path pixi.toml -e default bash dev/pytest-cli.sh vehicle_clustering --all
```

Documentation: [docs/index.html](docs/index.html).
