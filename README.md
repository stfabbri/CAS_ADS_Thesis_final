# CAS_ADS_Thesis_final
Applied Data Science Final thesis project


# Automated Lineament Detection from Digital Elevation Models (DEM) & Field Pictures
# Background

In geological sciences, it is of major interest how faults and folds are oriented in nature, since they can host potentially hazardous earthquakes. In this design report, we discuss how various types of input images (drone photos, Lidar-images, orthophotos) can be used to obtain lineaments (e.g. faults) in an automated way with a python-based algorithm and compare these results to a reference dataset created by a geologist. The different outputs (lineaments) are then compared to each other using performance indexes (such as the Jaccard score for image similarity) and are statistically analyzed. The output is additionally clustered with various methods such as k-means and dbscan. We investigate potential gains of having an automated algorithm and try to highlight the benefits of introducing more automatism and subjectivity to the geologist’s job. 

In the framework of this thesis, a python routine has been developed to successfully retrieve lineaments from a digital elevation model and orthophotos. The dataset from the python routine is then compared with the datasets created by the matlab-based algorithm. Furthermore, a geologist manually interpreted the orthophotos and created a dataset of lineaments, which will serve as a reference dataset. The produced dataset of lineaments are used as input for further analysis and statistical evaluation, including some unsupervised machine-learning algorithms for further interpretation of data

Hence, the aim of this CAS project is multi-fold, is split into 4 goals that want to
a)	Plot the input data and test various image enhancement techniques applied to the input data (satellite and drone based imagery)
b)	Create a python routine to retrieve lineaments (output) from various satellite and drone based imagery (input) using edge detection algorithms
c)	Analyze the output (lineaments) from DEMs and FIPHs
d)	Use unsupervised machine-learning algorithms to interpret data and compare the results with data from hand-picked (geologist) datasets


# GOAL A: Analyse DEM and Orthophotos and maniputlate and filter the data for image enhancement
Colab python file (GOAL_A_ImageEnhancement.ipynb) reads in digital elevation model (DEM), and hillshade pictures

-> Input Files are all in Folder: DEM and Hillshade; code accesses automatically the files in github

It performs some pre-processing steps, shapes the input data, plots the input data in various fashions and tests image enhancement techniques (e.g. filtering using fast-fourier transform, contrast enhancements, different degrees of image blurring). Image blurring usually helps to perform better edge detection results (Goal B).

Various filtering techniques are tested for edge detection preparation.


# GOAL B: Edge detection and lineament retrieval
Colab python file (GOAL_B_EdgeDetection.ipynb)

It reloads the pre-processed images and performs various ways to do edge detection of the image. We test the algorithms with different inputs. Image blurring usually helps to perform best at edge detection. The detected lineaments (x1,y1,x2,y2 - coordinates) are then stored in .csv - files and are exported to drive. The lineaments build the input for the data analysis in Goal C).

# GOAL C: Data Analysis
Colab python file (GOAL_C_DataAnalysis.ipynb)
It reloads the exported csv files with lineaments form Goal B) and performs various ways to analyse and illustrate the data (histograms, Rose diagrams etc.)

# GOAL D: Clustering
Colab python file (GOAL_D_Clustering.ipynb)
It reloads the exported csv files with lineaments from Goal B) and performs various ways to analyse and interpret the data with unsupervised machine learning algorithms (e.g. k-means etc.) https://scikit-learn.org/stable/modules/clustering.html

# Folders: Figures_Output Part 1 and 2
These folders contain all pictures created with the notebook from Part 1 and Part 2.

last change: 24.01.2022, stfabbri
