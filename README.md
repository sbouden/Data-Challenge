# Data-Challenge-Face-recognition-Idemia
### Fusion of algorithms for face recognition

The increasingly ubiquitous presence of biometric solutions and face recognition in particular in everyday life requires their adaptation for practical scenario. In the presence of several possible solutions, and if global decisions are to be made, each such single solution can be far less efficient than tailoring them to the complexity of an image.

In this challenge, the goal is to build a fusion of algorithms in order to construct the best suited solution for comparison of a pair of images. This fusion will be driven by qualities computed on each image.

Comparing of two images is done in two steps:
- 1st, a vector of features is computed for each image. 
- 2nd, a simple function produces a vector of scores for a pair of images. 
--> The goal is to create a function that will compare a pair of images based on the information mentioned above, and decide whether two images belong to the same person.


#### The properties of the dataset:
- A labelled set of training data
- A test set without labels
--> You should submit a .csv file with labels for each entry of this test set.

##### Training data:

The training set consist of two files, xtrain_challenge.csv and xtest_challenge.csv.

File xtrain_challenge.csv contains one observation per row which contains following entries based on a pair of images:

columns 1-13 - 13 qualities on first image;
columns 14-26 - 13 qualities on second image;
columns 27-37 - 11 matching scores between the two images.
File ytrain_challenge.csv contains one line with each entry corresponding to one observation in xtrain_challenge.csv, maintaining the order, and has '1' if a pair of images belong to the same person and '0' otherwise.

For each of these 38 variables, there are in total 9,800,713 training observations.

Training data, input (file xtrain_challenge.csv):
https://www.dropbox.com/s/618rb0wev4q84kj/xtrain_challenge.csv

Training data, output (file ytrain_challenge.csv):
https://www.dropbox.com/s/oph3w9sn3nmu376/ytrain_challenge.csv

##### Test data:
File xtest_challenge.csv has the same structure as file xtrain_challenge.csv.
There are in total 3,768,311 test observations.

Test data, input (file xtest_challenge.csv):
https://www.dropbox.com/s/fezxb6lrzass556/xtest_challenge.csv


#### The performance criterion¶
Consider the problem of the supervised classification with two classes labeled '0' and '1'. Many methods for supervised classification assign a new observation x to a class using the following rule:

g(x)={10 if f(x)≥t, otherwise.(1)
Threshold t is then chosen due to specific needs managing the trade-off between the true positive rate (TPR) and the false positive rate (FPR), depending on the cost of the corresponding mistakes.

Here, the performance criterion is TPR for the value of FPR = 10−4, or, speaking in other words, one needs to maximize the value of the receiver operating characteristic (ROC) in the point FPR = 10−4. The submitted solution file should thus contain the score for each observation.
