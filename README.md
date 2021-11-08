# Python Programming with Rasterio
## Assignment
In this assignment you will learn about the `rasterio` library. You will use a Landsat scene stores in a public AWS bucket. 


### Background
[`rasterio`](https://rasterio.readthedocs.io/en/latest/) is the most popular python library for reading and manipulating geospatial raster datasets. The `gdal` wrapper for python is also widely used but `rasterio` is considered more "pythonic". 

Be sure to install the following libraries if you haven't already (current tested versions in parentheses):
- `rasterio` (1.1.0)
- `pyproj` (2.6.1.post)
- `matplotlib` (3.4.3)

Recall that installation can be done in Anaconda Navigator by finding and installing the `rasterio` library in the list of packages.

### Instructions
For this assignment we will be following the tutorial at https://geohackweek.github.io/raster/04-workingwithrasters/. As you work through this tutorial, answer the following questions (each question/subquestion is worth equal points). Save all your python code in a file named `landsat.py` and include it in your branch.

1. rasterio profile
When first opening the raster, you are asked to print the profile. What is the python `type` of `src.profile`? 

2. Related to `src.profile` above:
List the key-value pairs and explain what they mean

3. What does this line do:
```
    thumbnail[thumbnail==0] = np.nan
```

4. What is a `COG` and why would you want to use one?


5. What is decimation?


6. The tutorial walks you through calculating the Normalized Difference Vegetation Index. Modify your function to calculate the Modified Normalized Difference Water Index, or NDWI. This formula uses the Green and SWIR bands which, for Landsat 8, are Band 3 and Band 6 respectively: `mNDWI = (Green - SWIR)/(Green+SWIR)`. 

    a. Write a function `calc_ndwi` and include it in your `landsat.py` file. 
    
    b. Take a screenshot of the overview showing the mNDWI, naming it `screencap_mndwi.png`

7. What is `pyproj` used for? Is there another library that you have used that could accomplish this function? 
Bonus: Include code for projecting a point using a library other than `pyproj`

8. How can you use `rasterio` to translate between image coordinates and real world coordinates?

9. Include a screenshot showing a plot of the NDVI difference plot, but make the plot an individual plot (not a 1x3) and change the color map to anything we haven't used already in this tutorial. See [this tutorial for examples](https://matplotlib.org/stable/tutorials/colors/colormaps.html).

10. Finally, reproject this to California State Plane, Zone 3, which is a local CRS that managers might use this with. Include this in your `landsat.py` script.

Save your work as you go as `landsat.py` and include it with your assignment.

### Deliverables

You should have answered the questions above (inline with the README.md is best), a single screenshot, and the script you produced:

- `README.md`
- `screencap_mndwi.png`
- `landsat.py` 
 
Include those in a branch named `rasterio` and submit a `Pull request` to merge with `master`. Do not merge!
