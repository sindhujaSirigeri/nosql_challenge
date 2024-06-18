# nosql_challenge
##Project Overview
This project involved analyzing food hygiene ratings data from the UK Food Standards Agency, using MongoDB to manage the data and Jupyter Notebook to perform the analysis. The data was evaluated to assist the editors of the food magazine, Eat Safe, Love, in determining where to focus their future articles.

## Setup and Execution
### Part 1: Database and Jupyter Notebook Set Up**
Imported the establishments.json data into a MongoDB database named uk_food and a collection named establishments: 
"mongoimport --db uk_food --collection establishments --file establishments.json --jsonArray"

### Part 2: Update the Database

1.  **Addition of New Restaurant**:
      -   Added a new restaurant, "Penang Flavours," to the database with the provided details.
        
2.  **Updating BusinessTypeID**:
    -   Retrieved the `BusinessTypeID` for "Restaurant/Cafe/Canteen" and updated the new restaurant document with this ID.
      
3.  **Removal of Dover Establishments**:
    -   Checked the number of establishments in Dover.
    -   Removed all establishments in the Dover Local Authority from the database.
    -   Verified the removal by recounting the documents.
      
4.  **Data Type Conversion**:
    -   Used `update_many` to convert `latitude` and `longitude` to decimal numbers.
    -   Converted `RatingValue` to integer numbers, while coercing non-numeric values to `null`.

### Part 3: Exploratory Analysis

1.  **Analysis Questions**:
    -   Determined which establishments had a hygiene score of 20.
    -   Identified establishments in London with a `RatingValue` of 4 or higher.
    -   Found the top 5 establishments with a `RatingValue` of 5, sorted by the lowest hygiene score, near "Penang Flavours".
    -   Counted the number of establishments with a hygiene score of 0 in each Local Authority area, sorted the results, and printed the top ten areas.
      
2.  **Results Presentation**:
    -   Each query's results were displayed using `count_documents` and `pprint`.
    -   Results were converted to a Pandas DataFrame, displaying the number of rows and the first 10 rows for each query.

## Conclusion
The analysis provided insightful data to assist the editors of Eat Safe, Love in their article planning. The use of MongoDB allowed efficient data handling and querying, while Jupyter Notebooks facilitated clear and reproducible analysis.

## Files

-   `NoSQL_setup_starter.ipynb`: Contains the database setup and initial data import.
-   `NoSQL_analysis_starter.ipynb`: Contains the queries and analysis for the magazine editors.
-   `establishments.json`: The dataset used for the analysis.

## How to Run
1.  Clone the repository from GitHub.
2.  Ensure MongoDB is installed and running on your local machine.
3.  Import the data using the provided `mongoimport` command.
4.  Open the Jupyter notebooks and run the cells sequentially to reproduce the analysis.

This project demonstrated the effective use of NoSQL databases for handling and analyzing real-world datasets, providing valuable insights for decision-making in the food industry.
