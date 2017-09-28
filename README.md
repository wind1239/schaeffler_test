# schaeffler_test
## Test 4
Different regression models are tested to find out that SVMs, Linear and ridge regression work pretty well for this data set. The model accuracy is verified by cross validation to ensure its genericness. 
#### Training
```
ipython -i regression_model_4.py testData4.csv
```
##### Comparison of different regression models' confidence
```
('linear regression', 0.99975667051268147)
('ridge regression', 0.99975448579514004)
('svm-linear', 0.99974844384657435)
('svm-poly', 0.90306540828055337)
('svm-rbf', 0.99943503958248603)
``` 
Linear regression is chosen finally
## Test 6 
The model uses a Gaussian Mixture Model(GMM) to cluster the given data purely because of the nature of the distribution.  Scikit tools provide the information-theoretic criteria for each GMM model depending on the number of clusters and the covariance type. Iterating over a range of possible clusters and different covariance types, the model is selected with high information-theoretic criteria score. The figure below shows the prediction of the final trained model which clusters the given data in to 5 clusters. Run this script to check for other data.
#### Training
```
ipython -i clustering.py testData6.csv
```
#### Loading existing Model
```
import numpy,pickle
X = np.loadtxt(file, delimiter=';', skiprows=1)
pickle_in = open('clustering_test6.pickle','rb')
clf = pickle.load(pickle_in)
labels = clf.predict(X)
```
![Alt text](/test6/clustering.png?raw=true "Results")



