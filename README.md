# Welcome to the Spotify-Recommender-System Repository

## About
This is a Mini-Project for SC1015 (Introduction to Data Science and Artificial Intelligence) which aims to create an effective and efficient music recommender system. 

For a detailed walkthrough, please view the source code in order from:

Part 1: Genre Classification Model 
- Our attempt at feature engineering to create genre labels for our curated playlist where song recommendations from our system are based on
- Uses dataset.csv
- Exports mapper.pkl and multinomial_logistic_regression_model.pkl which is used for genre classification in Part 3 (both files attached in the Repo)

Part 2: Music Popularity Model
- Our analysis of feature importances for song popularity, which we hypothesise as a heuristic for feature selection in our Recommender System to streamline training efficiency
- Uses full_spotify_playlist_dataset.csv

Part 3: Music Recommender System
- We curated our own Spotify playlist and made API calls to fetch the metadata of each song which we compiled into our own dataset. 
- We created Autoencoder network to reduce dimensionality of data 
- Uses spotify_playlist_dataset1.csv, spotify_playlist_dataset2.csv, mapper.pkl and multinomial_logistic_regression_model.pkl


## Data Source
dataset.csv: from Spotify Dataset on kaggle (https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset/data)

spotify_playlist_dataset1.csv, spotify_playlist_dataset2.csv: created via Spotify API call and using helper method get_audio_info_from_playlist.

full_spotify_playlist_dataset.csv: Created by combining the two files above to form our base pool of songs for recommendation

## Contributors
- Syed Ali Redha Alsagoff - Music Recommender System (incl. Spotify API and Recommender System), Slides, Documentation
- Huang Yongjian - Genre Classification Model, Slides, Documentation, Video Presentation
- Ma Jinlin - Music Popularity Model, Slides, Video Presentation, Video-editing

## Problem Definition
- How can companies maximize the use of machine learning to recommend quality songs efficiently?

## Models Used
- Genre Classification Model: XGBoost Classifier, Random Forest, Multinomial Logistic Regression
- Music Popularity Model: XGBoost Regressor and Classifier 
- Music Recommender System: Autoencoder and K-Nearest Neighbour 

## Conclusion
Firstly, the use of Weighted Autoencoders can help improve training efficiency without significant performance cost when using numerical metadata.  

Secondly, to make a more robust recommender system, we can integrate collaborative filtering with our existing content-based filtering approach. The implementation of collaborative filtering, which seeks to filter out music suggestions to a user based on how similar users react, can help to enhance our model further to personalise recommendations. 

Thirdly, we can broaden the types of data used. Beyond the structured data for training, we can also use lyric and audio data to enhance feature selection and potentially improve the quality of recommendations to users. However, this will come at the expense of more compute, which leads to our fourth point. 

To balance cost and performance, we recommend similar dimensionality reduction techniques such as the use of Mel-Frequency Cepstral Coefficients (MFCCs) and the Singular Value Decomposition (SVD) to encode audio and lyric data respectively. 

## Main learning points
- Feature Engineering
- Data Prepocessing techniques such as MultiLabelBinarizer, LabelBinarizer etc to one-hot encode categorical features
- Creation of Preprocessing Pipeline using DataFrameMapper from sklearn-pandas
- Use of state-of-the-art XGBoost model
- Random Forest and Multinomial Logistic Regression from sklearn
- Evaluation Metrics for Multiclass Classification: AUC-ROC
- Exporting Models via Pickle
- Extracting Feature Importance from Model
- Spotify API Usage
- AutoEncoder from TensorFlow
- K-Nearest Neighbour from sklearn.neighbors
- Collaborating using GitHub

## References
- T. Chen and C. Guestrin, "XGBoost: A Scalable Tree Boosting System," in Proceedings of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining, 2016, pp. 785-794, doi: 10.1145/2939672.2939785.
- M. Schedl, ‘Deep Learning in Music Recommendation Systems’, Front. Appl. Math. Stat., vol. 5, doi: 10.3389/fams.2019.00044.
- F. Ricci, L. Rokach, and B. Shapira, Eds., Recommender Systems Handbook. New York, NY: Springer US, 2022. doi: 10.1007/978-1-0716-2197-4.
- V. Tiwari, "MFCC and its applications in speaker recognition," International Journal on Emerging Technologies, vol. 1, no. 1, pp. 19-22, 2010.
- P. C. Hansen, "The truncatedSVD as a method for regularization," BIT Numerical Mathematics, vol. 27, no. 4, pp. 534-553, 1987. doi: 10.1007/BF01937276.