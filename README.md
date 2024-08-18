
# Movie Recommendation System

This project implements a movie recommendation system using TensorFlow. The system is based on collaborative filtering, where a Restricted Boltzmann Machine (RBM) is trained to generate movie recommendations for users based on their past ratings.

## Overview

The notebook processes a dataset of movie ratings and uses a machine learning model to recommend movies to users. The main steps involved are:

1. **Data Preparation**:
    - Load and preprocess the dataset.
    - Normalize the ratings.
    - Create a matrix of user ratings.

2. **Model Training**:
    - Build and train a Restricted Boltzmann Machine (RBM) model.
    - Track and plot the training error over epochs.

3. **Model Saving and Retrieval**:
    - Save the model's weights and biases for future use.
    - Load the saved model parameters to make predictions.

4. **Generate Recommendations**:
    - Use the trained RBM model to generate movie recommendations for users.
    - Merge the recommendations with the original ratings data to compare predicted and actual ratings.

## Dataset

The dataset used in this project is a collection of movie ratings by different users. It contains the following columns:

- `user_id`: Unique identifier for each user.
- `movie_id`: Unique identifier for each movie.
- `rating`: The rating given by a user to a movie, on a scale of 0-5.

## Steps

### 1. Data Preparation

- **Load the Data**: The dataset is loaded from a text file and stored in a pandas DataFrame.
- **Remove Duplicates**: Duplicates in the dataset are removed based on `user_id` and `movie_id`.
- **Pivot the DataFrame**: The dataset is pivoted to create a matrix of user ratings.
- **Normalize the Ratings**: Ratings are normalized to fall within the range [0, 1].

### 2. Model Training

- **Define Model Parameters**: The RBM model is initialized with parameters including visible units (movies) and hidden units (features).
- **Train the Model**: The model is trained over a series of epochs. During training, the reconstruction error is tracked and used to assess model performance.

### 3. Model Saving and Retrieval

- **Save Model Parameters**: After training, the weights and biases of the model are saved as CSV files.
- **Load Model Parameters**: The saved weights and biases can be reloaded to reconstruct the model without re-training.

### 4. Generate Recommendations

- **Get User Recommendations**: The trained model is used to predict movie ratings for a specific user.
- **Sort and Merge Recommendations**: The recommendations are sorted by score, and merged with the original dataset to compare with actual ratings.

## How to Run

1. **Install Dependencies**:
    - Ensure you have Python installed with the following libraries:
    ```bash
    pip install pandas tensorflow numpy matplotlib
    ```

2. **Execute the Notebook**:
    - Open the notebook in Jupyter or any other compatible IDE.
    - Run each cell sequentially to load data, train the model, and generate recommendations.

3. **Test Recommendations**:
    - Use the `get_user_recommendations()` function to generate recommendations for a specific user.
    - Evaluate the recommendations by comparing the predicted scores with actual user ratings.

## Results

- The RBM model is trained over 5 epochs, and the reconstruction error is tracked to monitor the model's performance.
- After training, the model can generate movie recommendations for users based on their past ratings.
- The results include the predicted scores for movies, which can be compared with the user's actual ratings.

## Conclusion

This project demonstrates how to build and train an RBM model using TensorFlow for movie recommendation purposes. The model effectively captures user preferences and can be used to predict ratings for movies that a user has not yet rated.

