#

![GeoSpark Logo](https://github.com/DataSystemsLab/GeoSpark/raw/master/GeoSpark_logo.png)

|     Stable    | Latest | Source code|
|:-------------:|:------|:------:|
|[![Maven Central with version prefix filter](https://img.shields.io/maven-central/v/org.datasyslab/geospark.svg)](./download/GeoSpark-All-Modules-Maven-Central-Coordinates.md) | [![Sonatype Nexus (Snapshots)](https://img.shields.io/nexus/s/https/oss.sonatype.org/org.datasyslab/geospark.svg)](./download/GeoSpark-All-Modules-Maven-Central-Coordinates.md) | [![Build Status](https://travis-ci.org/DataSystemsLab/GeoSpark.svg?branch=master)](https://travis-ci.org/DataSystemsLab/GeoSpark)|

[GeoSpark@Twitter](https://twitter.com/GeoSpark_ASU) || [GeoSpark Discussion Board](https://groups.google.com/forum/#!forum/geospark-discussion-board) || [![Join the chat at https://gitter.im/geospark-datasys/Lobby](https://badges.gitter.im/geospark-datasys/Lobby.svg)](https://gitter.im/geospark-datasys/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## News!

* A research paper about ["GeoSparkSim: A Microscopic Road Network Traffic Simulator in Apache Spark"](http://www.public.asu.edu/~jiayu2/geospark/publication/geosparksim-mdm-2019.pdf) is accepted to MDM 2019, Hong Kong China. The next release of GeoSpark will come with a built-in scalable traffic simulator. Please stay tuned!
* A 1.5-hour tutorial about "Geospatial Data Management in Apache Spark" was presented by Jia Yu and Mohamed Sarwat in ICDE 2019, Macau, China. Visit [our tutorial website](https://jiayuasu.github.io/geospatial-tutorial/) to learn how to craft your **"GeoSpark"** from scratch.
* GeoSpark 1.2.0 is released.

## Companies are using GeoSpark 

(incomplete list)

[<img src="https://www.dataiku.com/static/img/partners/LOGO-Blue-DME-PNG-3.png" width="200">](https://www.bluedme.com/) &nbsp;&nbsp; [<img src="https://www.gyana.co.uk/images/logo@4x.png" width="200">](https://www.gyana.co.uk/) &nbsp;&nbsp; [<img src="https://mobike.com/global/public/invitation__footer__logo.png" width="150">](https://mobike.com)

Please make a Pull Request to add yourself!

## Introduction

GeoSpark is a cluster computing system for processing large-scale spatial data. GeoSpark extends Apache Spark / SparkSQL with a set of out-of-the-box Spatial Resilient Distributed Datasets (SRDDs)/ SpatialSQL that efficiently load, process, and analyze large-scale spatial data across machines.

### GeoSpark contains several modules:

| Name  |  API |  Spark compatibility|Introduction|
|---|---|---|---|
|Core  | RDD  | Spark 2.X/1.X  |SpatialRDDs and Query Operators. |
|SQL  | SQL/DataFrame  | SparkSQL 2.1+ |SQL interfaces for GeoSpark core.|
|Viz |  RDD, SQL/DataFrame | RDD - Spark 2.X/1.X, SQL - Spark 2.1+|Visualization for Spatial RDD and DataFrame.|
|Zeppelin |  Apache Zeppelin | Spark 2.1+, Zeppelin 0.8.1+|GeoSpark plugin for Apache Zeppelin|

## Impact

### GeoSpark Downloads on Maven Central

GeoSpark ecosystem has around 8K - 10K downloads per month.

<img src="image/geospark-stat.png" width="500"/>

## Features

* ==Spatial RDD==
* ==Spatial SQL==
```SQL
SELECT superhero.name
FROM city, superhero
WHERE ST_Contains(city.geom, superhero.geom)
AND city.name = 'Gotham';
```
* ==Complex geometries / trajectories==: point, polygon, linestring, multi-point, multi-polygon, multi-linestring, GeometryCollection
* ==Various input formats==: CSV, TSV, WKT, WKB, GeoJSON, NASA NetCDF/HDF, Shapefile (.shp, .shx, .dbf): extension must be in lower case
* ==Spatial query==: range query, range join query, distance join query, K Nearest Neighbor query
* ==Spatial index==: R-Tree, Quad-Tree
* ==Spatial partitioning==: KDB-Tree, Quad-Tree, R-Tree, Voronoi diagram, Hilbert curve, Uniform grids
* ==Coordinate Reference System / Spatial Reference System Transformation==: for exmaple, from WGS84 (EPSG:4326, degree-based), to EPSG:3857 (meter-based)
* ==High resolution map==: Scatter plot, heat map, choropleth map

## GeoSpark language support

| Language | Supported GeoSpark modules | Tutorial |
|:--------:|:--------------------------:|:--------:|
|   Scala  |   RDD, SQL, Viz, Zeppelin   | [RDD](./tutorial/rdd), [SQL](./tutorial/sql), [Viz](./tutorial/viz), [Zeppelin](./tutorial/zeppelin)|
|   Java   |        RDD, SQL, Viz       |[RDD](./tutorial/rdd), [SQL](./tutorial/sql), [Viz](./tutorial/viz)|
|    SQL   |          SQL, Viz, Zeppelin          |[SQL](./tutorial/sql), [Viz](./tutorial/viz), [Zeppelin](./tutorial/zeppelin)|
|  Python  |             SQL            |[SQL](./tutorial/geospark-python)|
|     R    |             SQL            |[]()|

## GeoSpark Visualization Extension (GeoSparkViz)
GeoSparkViz is a large-scale in-memory geospatial visualization system.

GeoSparkViz provides native support for general cartographic design by extending GeoSpark to process large-scale spatial data. It can visulize Spatial RDD and Spatial Queries and render super high resolution image in parallel.

More details are available here: [Visualize Spatial DataFrame/RDD](tutorial/viz)

**GeoSparkViz Gallery**


<img style="float: left;" src="http://www.public.asu.edu/~jiayu2/geospark/picture/usrail.png" width="250">
<img src="http://www.public.asu.edu/~jiayu2/geospark/picture/ustweet.png" width="250">

[Watch the high resolution version on a real map](http://www.public.asu.edu/~jiayu2/geospark/picture/overlay.html)

<img src="http://www.public.asu.edu/~jiayu2/geospark/picture/heatmapnycsmall.png" width="500">

### Research

GeoSpark development team has published many papers about GeoSpark. Please read [Publications](publication). 

GeoSpark received an evaluation from PVLDB 2018 paper ["How Good Are Modern Spatial Analytics Systems?"](http://www.vldb.org/pvldb/vol11/p1661-pandey.pdf) Varun Pandey, Andreas Kipf, Thomas Neumann, Alfons Kemper (Technical University of Munich), quoted as follows: 
> GeoSpark comes close to a complete spatial analytics system. It also exhibits the best performance in most cases.
