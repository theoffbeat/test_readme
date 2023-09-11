# The Stage Volume Program

## How to use the program
The Stage Volume program is accessed by the user as a Command Line Interface (CLI). There are certain benefits and limitations to a CLI. Therefore, the user must enter commands carefully to avoid errors and ensure proper usage.

* A Python Environment that contains the arcpy and Pandas Library is required.
* Provide the commands and arguments (see the table below for reference). They can be provided in any order.
* The field command is the name of the field in your shapefile.
* There can be multiple raster files, the Dem Layer, and the program will combine them.
* User must provide the full path for the input folder.
* For all other inputs, the user can provide the full path to the required files, or simply the folder path if the folders and files are contained within the input folder.
* Example:
    * Input folder “C:\Users\e1gisabc\Project Name”
    * If the remaining files and output folder are located within a folder in the “Project Name” folder: “Shape Layers\projectAreas.shp”
    * If the remaining files and output folder are located outside the “Project Name” folder “C:\Uses\e1gisabc\Shape Layers\projectAreas.shp”
* Output folder
    * A folder is specified by the user, the files will be saved to that path.
    * No folder is specified by the user, a folder will be created with files saved to that path.
    * The results will be outputted in an Excel format for each boundary.

## CLI Commands
| Command       | Long Name         | Short Name | DataType | Required | Example                      |
| ------        | ---------         | ---------  | -------- | -------- | -------                      |
| Shape Layer   | `--shape_layer`   | `-sl`      | String   | Yes      | `-sl "ModelArea.shp" `       |
| Column Field  | `--field`         | `-f`       | String   | Yes      | `-f "Shape_Length" `         |
| Dem Layer     | `--dem_layer`     | `-dl`      | String   | Yes      | `-dl "USGS01.tif" `          |
| Max Depth     | `--depth_max`     | `-dm`      | Integer  | Yes      | `-dm 14 `                    |
| Input Folder  | `--input_folder`  | `-i`       | String   | Yes      | `-i "C:\Users\ProjectName" ` |
| Output Folder | `--output_folder` | `-o`       | String   | No       | `-o "C:\Users\Results" `     |
| Debug Mode    | `--debug`         | `-d`       | Boolean  | No       | `-d `                        |

Full example with parameters of entering arguments using **LONG** names:

`$ python stage_volume.py –-shape_layer “ModelArea.shp” –-field “Shape_Length” –-dem_layer “USGS01.tif” –-depth_max 14 –-input_folder “C:\Users\user_id\Amazing Project” --output_folder “C\Users\user_id\Project Output” `

Full example with parameters of entering arguments using **SHORT** names:

`$ python stage_volume.py –sl “ModelArea.shp” –f “Shape_Length” –dl “USGS01.tif” –dm 14 –i “C:\Users\user_id\Amazing Project” -o “C\Users\user_id\Project Output” `

## Purpose of the program
The purpose of the program is to provide a Shapefile (.shp) and 1 or more Rater Files (preferably in the TIF (.tif) file format) and determine the stage volume for each section of the Shapefile.

## Known limitations
* Requires the installation of ESRI ArcGIS Pro as the program uses the arcpy library.
* Requires the installation of the Pandas library.
* The program requires linear access to the shapefiles for processing and is time consuming. However, it is still faster, and less error prone, to performing the process manually and the program will inform the user of its progress. 


