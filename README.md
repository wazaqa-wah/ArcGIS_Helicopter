# Advanced GIS Class Final Project

This repo contains all the codes that used to pull data from OpenSky API, data cleaning, generate trajectory, figuring out helicopter trips, etc. 
If you want to work with OpenSky API, I hope they can help you.

## Description of the project

The inspiration of the project came from another project that I did with BetaNYC during my internship there. We were looking at helicopters in Manhattan, but due to the limitation of technology and staffing, we were not able to create the dashbaord on NYC helicopter information that we wanted. However, me and decided to take on this idea and try to make it happen. For me and Jiacheng, we are primarily interested in producing a 3D visual of the helicopter flying routes, some geospatial analysis on the data (places they like to visit, airports they like to stop by), and maybe produce some time series graphs to show when the city is the busiest with helicopters (volumn of helicopters in a perimiter near a location of interest). The 3D graphs and spacial analysis as well as the dashboard are all done in ArcGIS Online/ArcGIS Pro, however, all the data analysis are all donw in Python.

This repo contains all the code documents for data clearning and analysis in that are done in Python. I will break them down by individual documents to help you understand what they all do.


## Python codes

### Query API

* This is the file to pull API data from Opensky API using ssh. You can also use Request, which is most basic way and Opensky API has a good documentation for it. This code was shared by my former supervisor Zhi from BetaNYC, and we really thank him. 
* This code created a for loop so that you can get data for more than the time limiation of Opensky API (which is 2 hours max I think).
* Due to the inconsistancy of the API (for us at least), we only were able pulled helicopter information from 7/2/2022, but you can modify the code so that it gets data for more than one day.
* Keep in mind that you have to run the following code in terminal: ssh -p 2230 -l YOURUSERNAME data.opensky-network.org;YOURPASSWORD

### Helicopter data cleaning and count volume

* This is the file to clean the dataset we downloaded using the query code. Most of the blocks in this files are annotated with what it does and stuff, os things shouldn't be too confusing.
* Few important feature of this code include: identify unique trips took by individual helicopter and assign each trip its own unique index, starting from 0 each trip; generate trajectory for each helicopter trip so that it has it's own geometry (it very helpful if you want to do geoanalysis in Python); count helicopter trip volumn in a 700 meter (yes we love the metric system) radius around locations of interest.

### Count helicopter trips

* This awesome documents allows us to generate indexes for each helicopter trips in a way that ArcGIS Pro can understand. We faced the issue of ArcGIS connect all the dots disregarding the individual trips, so it looks pretty ugly and hard to render when we try to upload it on to it's online dashboard platform. So we wrote a for loop to give each trip consistent ID.


## Helps and thanks

Thanks to Zhi Keng He from BetaNYC who provided us his username and password to access Opensky API. Thanks to Zhi again for providing us with code and essential help and guidance during my internship so that I was able to write these amazing codes. Thanks to my friend, project partner, and best bro Jiacheng Chen to do this project with me. You are so encouraging and patient with me, and you pushed this project to another level. So many times that I wanted to say "nah this would do" you insisted on actually figuring things out. Finally, thanks to John Lauermann. You truely believed that we could do finish this project. Everytime you tell us how good it is even though we have so little to show just makes us more motivated. You are a true mentor to the both of us

## Authors

Jiacheng Chen
GitHub:[JCC](https://github.com/Coalllball)

Ziqi Wang
GitHub:[Ziqi](https://github.com/wazaqa-wah)

Special thanks: Zhi Keng He
GitHub:[Zhi Keng He](https://github.com/zhik)

