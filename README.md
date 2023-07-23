# MovieRec
A movie recommendation system built using python


# Movie Recommender System

This Python code implements a simple content-based movie recommender system. It uses movie metadata, such as genres, keywords, cast, crew, and overview, to generate movie recommendations based on similarities between movie tags.

## Prerequisites

Before running this code, ensure you have the following installed:

- Python 3.x
- Required Python libraries: numpy, pandas, ast, nltk, sklearn

You can install the required libraries using `pip`:
```bash
pip install numpy pandas nltk scikit-learn
```

## How to Use

1. Clone or download the repository to your local machine.

2. Ensure that the `tmdb_5000_movies.csv` and `tmdb_5000_credits.csv` files are present in the same directory as the Python script.

3. Run the Python script. The script will perform the following steps:

## Data Preprocessing

- Read the CSV files `tmdb_5000_movies.csv` and `tmdb_5000_credits.csv` using pandas.
- Merge the two dataframes based on the "title" column.
- Extract important columns: 'movie_id', 'title', 'overview', 'genres', 'keywords', 'cast', and 'crew'.
- Convert genres, keywords, cast, and crew columns from string representation to lists of strings using `ast.literal_eval`.
- Handle missing values by dropping rows with NaN values.
- Remove any duplicates from the dataframe.
- Process the 'overview', 'genres', 'keywords', 'cast', and 'crew' columns by tokenizing the text and converting to lowercase, removing spaces, and extracting only the first three elements from the 'cast' column.

## Creating Tags

- Combine the 'overview', 'genres', 'keywords', 'cast', and 'crew' columns to create a new 'tags' column.
- Preprocess the 'tags' column by stemming and converting the text to lowercase.

## Generating Movie Vectors

- Use CountVectorizer from sklearn to convert the 'tags' column into numerical vectors.

## Calculating Similarity

- Use cosine_similarity from sklearn to calculate the similarity between movie vectors.

## Movie Recommendation

- Create a function `recommend(movie)` that takes a movie title as input and recommends five similar movies based on the calculated similarity.
- Print the recommended movie titles.

## Saving Data

- Save the processed dataframe and similarity matrix as pickle files for later use.

Please note that this is a basic content-based movie recommender system and may not produce the most accurate recommendations. The recommendations are based solely on movie metadata and do not take into account user preferences or ratings. For more advanced recommendation systems, collaborative filtering and other methods can be used to enhance the accuracy and personalization of recommendations.

For more details on the implementation, you can refer to the original Colaboratory notebook where this code was generated:
[Original Colaboratory Notebook](https://colab.research.google.com/drive/13KKhe7oOeIoeDuF7ufGZbPJ6ifEiwFb_)
