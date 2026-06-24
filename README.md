IMDb Data Integration Project

Module:
-------
B142 Data Integration -- GISMA University of Applied Sciences


Project Overview:
-----------------
An end-to-end ETL pipeline built with Apache Spark on Databricks that
integrates three IMDb public datasets. The project cleans, transforms,
and analyzes movie metadata, ratings, and crew information to identify
key characteristics associated with highly rated films.

Business Question:
------------------
How can movie metadata, ratings, and crew information be integrated 
using Apache Spark to identify characteristics associated with highly 
rated films?


Dataset Source:
---------------
IMDb Non-Commercial Datasets
URL: https://developer.imdb.com/non-commercial-datasets/
     (Direct download: https://datasets.imdbws.com/)

Datasets Used:
  * title.basics.tsv  - Movie metadata (titles, genres, release year, runtime)
  * title.ratings.tsv - Average rating and vote count per title
  * title.crew.tsv    - Director and writer identifiers per title


ETL Pipeline & Stages:
----------------------
IMDb TSV Files -> Data Loading -> Data Cleaning -> Data Integration -> 
Parquet Storage -> Genre Normalization -> Spark SQL Analysis -> Visualizations

1. Data Loading       - Load raw TSV files into Spark DataFrames.
2. Data Cleaning      - Handle '\N' null values, filter for movie formats only,
                        and explicitly cast data types.
3. Data Integration   - Execute inner joins across all three datasets utilizing
                        the primary key 'tconst'.
4. Save to Parquet    - Persist the integrated dataset in an optimized columnar format.
5. Genre Normalization- Explode multi-value genre strings into individual rows for
                        accurate categorical analysis.
6. Spark SQL Analysis - Execute five distinct analytical queries targeting performance metrics.
7. Visualizations     - Generate five charts using Matplotlib and Pandas to communicate findings.


Technologies Used:
------------------
* Platform:       Databricks (Free / Community Edition)
* Engine:         Apache Spark / PySpark & Spark SQL
* Languages:      Python 3, SQL
* Storage Format: Apache Parquet
* Libraries:      Pandas, Matplotlib
* Version Control:GitHub


Key Findings:
-------------
* Top Genres:          News, Documentary, and Biography achieved the highest average
                       ratings overall.
* Audience Engagement: Drama generated the highest volume of audience engagement (vote counts).
* Industry Growth:     Global movie production increased significantly after the year 2000.
* Rating Distribution: The vast majority of movies received average ratings clustered
                       between 5.0 and 7.0.


Repository Contents:
--------------------
* IMDb_Data_Integration_Project_Final.ipynb  - Complete Databricks / Jupyter Notebook
* Visualisation PNG files                    - Exported charts showing key findings
* README.txt                                 - Project documentation


How to Run:
-----------
1. Upload the three IMDb TSV files (title.basics.tsv, title.ratings.tsv, 
   title.crew.tsv) to your Databricks Volume or DBFS storage.
2. Update the input file paths in Section 2 of the notebook to match 
   your specific storage location.
3. Run all cells sequentially (Cell -> Run All).

========================================================================
