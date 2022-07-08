# Miniproject 2

### [Assignment](assignment.md)
## Notebook
The file containing my notebook with the code written is included [here](notebooks/mini-project-2.ipynb).

## Project/Goals
- Chose a location that I was interested in and used the FourSquare and Yelp API to pull names, locations, and ratings for places I was interested in(bars, restaurants, dessert shops)
- Created a dataframe from the information I gathered
- Transferred the dataframes I created into an SQLite3 database where I could then join the tables and query for information
- Analyze the data to reach some conclusions about the API's I worked with and the data I found

## Process
### 1. Search through FourSquare and Yelp documentation
This was done to determine which URL/URL's I would need to work with to find the information I was interested in.
### 2. Parse through the json.() of the API
Once I had successfully got my data from FourSquare and Yelp, I converted the data to json format and parsed through it for the information I wanted, such as: name, location, rating.
### 3. Convert the data to a dataframe
Using pandas I then converted all the information I had into a dataframe that was intuitive and simple to look at.
### 4. Store the dataframe information into SQL database
In my jupyter notebook, I created a connection to SQLite database so I now had a database on my local machine. After this I went on to convert my dataframes into tables in the database, resulting in a table for my FourSquare information, and another table for my Yelp information.
### 5. Lastly, finding the top 10 rated locations 
For this step, I already had two tables, one for each API, that contained the information about the restaurants and did a union between them to combine them into one table I could query from, I ordered it by rating and limited it to 10 and got the top 10 rated locations!

## Results
Looking at the API's, Yelp got me more results but because im familiar with the area that I queried, I know that some of the places it returned are no longer actually there, leading me to believe Yelp has some outdated information. Both API's seemed to be missing information on the area however, as many restaurants I know should have been included were not there. In terms of working with the API documentation, I preferred FourSquare as they made it really easy on their site to look for the information you want and build a URL. Actually parsing through the information actually felt easier on the Yelp json, however I was hoping that the Yelp API would have a broader category for restaurants but instead they were more specific with the name they gave to their categories e.g: 'Pizza' instead of simply 'Restaurant'.

## Challenges 
I felt that with previous exercises, working with API's in this mini-project felt easier since I had already seen much of what I had to do. However, I did find it hard to find the proper way to structure my get request specifically for Yelp, as I wasnt sure how my parameters for search should go in or how I would include my API key, meanwhile FourSquare included in their documentation how to do this, so it was much easier for their API. I also struggled with Yelp and FourSquare having different names for the same establishments, so having distinct data in, for example, the union between the two tables would be harder. The two API's also had different formats for the type of the places, which made filtering by type much harder. Also, FourSquare confused me for example with [this](images/thairest.PNG), where Thai restaurant is a sub-category under restaurant but [here](images/notrest.PNG) it didnt include the category of restaurant above Thai restaurant like it did for other places.

## Future Goals
- If I had more time, I would've liked to create a types column so I could seperate bars from restaurants and dessert places from those two as well. 
- Creating more tables in my SQL database, for example for location
    - Adding in data for city and province (even though for this assignment it wouldnt be useful since we used a 1km radius)