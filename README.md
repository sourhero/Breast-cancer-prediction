# Breast-cancer-prediction


Description of research question / issues (either scientific or statistical question): 
The epidemic of breast cancer has been plaguing humanity for a long period of time, in fact the first incident of breast cancer has been recorded in Egypt around 1600 BC. It has been uncovered from an ancient text found in 1860 in an Egyptian tomb describing eight cases of tumours of the breast (1). It is known to be caused by biological factors such as age and skin type. etc, other factors could be environmental exposure to UV or fine particulate matter,etc or lifestyle related factors like diet, and alcohol etc. (2). 
Most people are susseptable to these factors so detection of the cancer at early stages are vital to an effective prevention strategy, a study from cancer reasearch uk states that "More than 90% of women diagnosed with breast cancer at the earliest stage survive their disease for at least 5 years compared to around 15% for women diagnosed with the most advanced stage of disease" (3). An effective form of early detection is the fine needle aspirinate which is a type of biopsy procedure, this helps collect breast tissue samples to further diagnose between benign and Malignant cancer (4). 
Fine needed is essential because, proper use of FNA can prevent unnecessary surgery in nonsurgical conditions such as infections, lymphoproliferative disorders, and metastatic disease while providing material for ancillary tests such as culture, FCM, cytogenetic analysis, and molecular testing (5) 
It can tell us if the tumour is malignant or benign, benign cells are not cancerous and wont spread compared to malignant cells which are cancerous and would spread to other tissues (6). 
Objective: To analyze the characteristics of the cell nuclei from a digitized image of a fine needle aspirate (FNA) of a breast mass and determine the following. 
a) radius (mean of distances from center to points on the perimeter) b) texture (standard deviation of gray-scale values) c) perimeter d) area e) smoothness (local variation in radius lengths) f) compactness (perimeter^2 / area - 1.0) g) concavity (severity of concave portions of the contour) h) concave points (number of concave portions of the contour) i) symmetry j) fractal dimension ("coastline approximation" - 1) 
Then determine if it is benign or malignant, through diagnosis. Since the diagnosis procedure requires more time, it is important to determine the cancer through predictive model based on the characteristics alone. 
Description of data: Breast cancer data from Wisconsin has been used to create this predictive model, which has 569 recordings of cell nuclei with 357 benign, 212 malignant. These recordings include the following characteristics of the nuclei: 
a) radius (mean of distances from center to points on the perimeter) b) texture (standard deviation of gray-scale values) c) perimeter d) area e) smoothness (local variation in radius lengths) f) compactness (perimeter^2 / area - 1.0) g) concavity (severity of concave portions of the contour) h) concave points (number of concave portions of the contour) i) symmetry j) fractal dimension ("coastline approximation" - 1) 
In addition to these means of the nuclei, the data provided the standard error of the nuclei, and the "worst" or largest (mean of the three largest values) of these features were computed for each image. 
Descriptive statistics 
Boxplots 
Because data was measured on totally different scales, it was normalized (every vector re-scaled to a scale of 0 to 1) to produce comprehensible boxplots. We divided data into 3 groups: Mean, SE, Worst, and created boxplots for each. 
0.0 
0.1 
0.2 
0.3 
0.00 
0.05 
0.10 
0.15 
radius_se 
F--0:1 DODO 
oo 
radius_mean 
--- TOO 
-- 
--- 
--- 
00: 
0 
DODC----- 
perimeter_se 
perimeter_mean 
F--00:00:00 
- 
- 
- 
- 
0 
000 0 
0 
0 
0 O WRITE 
--- 
Worst group 
0 
smoothness_se 
smoothness_mean 
E-0:10 000 
SE group 
Mean group 
000 
0 
0 
--- CHI DOO 
concavity_se 
concavity_mean 
--00000000 
00 OWKOXO --- 
- 
- 
- 
- 
OOD-------------- 
OOO 000--- 
O 
000 C10 
0 
GIDO 0 
0 
UUELE 
symmetry_se 
symmetry_mean 
E- 
COICEDO 
F- 
MO) 
DICOD 
0 
0 
0 
0 
0.15 
Ooo 
00 00 00 
0 
0000 0 0 
000 
0.10 
- 
- 
0 
- 
- 
OOOO---- 
--- 1000000 
- 
-----------HOO 
-- DOO 
W 
- 
E--O00000 
-- MD 
- 
- 
- 
0.05 
- 
- 
- 
- 
0.00 
radius_worst 
perimeter_worst 
smoothness_worst 
concavity_worst 
symmetry_worst 
The main conclusions based on boxplots are: 
• 
There are many upper outliers in every group; SE group has the most outliers, and those outliers have the highest variance as compared to outliers from other 2 groups; Mean and Worst group have a much larger interquartile range than SE group which has very 
similar interquartile range for every variable; Concavity and Concave.points are 2 variables with the highest variance in Mean and Worst groups; Fractal_dimension and Smoothness are 2 variables with the lowest variance in Mean and Worst groups; Every variable is significantly skewed to the right in every group. 
Correlation 
Using 0.7 as a barrier for correlation, with >0.7 meaning the 2 variables are strongly linearly related, and <0.7 meaning the 2 variables are not strongly linearly related, we calculated that only 70 out of 400 pairs of variables are strongly linearly correlated. 
Then we divided data into 3 interaction subgroups: Mean_se, Mean_worst, Se_worst, and calculated correlation matrices for each of those (those are available in R markdown file) - those are the correlations between Mean, SE, and Worst groups for each variable pair. In the table, the number of strongly and average/weakly correlated pairs of variables is presented: 
Mean_se 
Mean_worst 
Se_worst 
Strong corr (>0.7) 
27 
92 
Average/Weak corr93 (<0.7) 
As we see, Mean and Worst groups have a better correlation that SE and any of the other 2. This means that Mean and Worst groups would have a more similar predictive power than SE. 
Lastly, we plotted all the variables within each group against each other: 
Mean group 
10 20 30 40 
500 
2000 
0.05 
0.25 
0.00 0.10 0.20 
0.05 
0.08 
radius_ 
man 
10 25 
35 
asune_m 
10 
OS 
_man 
500 
MESMO 
0.06 
NIINITANIE 
bonuscirness mer 
0.05 
Concity mear 
0.0 0.4 
oncepts med 
0.00 
Symmetry me 
0.10 
El dimensioni me 
90'0 
10 
20 
50 
150 
0.06 
0.12 
0.0 
0.2 
0.4 
0.10 0.20 
0.30 
SE group 
1 
3 
5 
0 
200 
500 
0.00 
0.08 
0.00 
0.03 
0.000 
0.020 
radius 20 
0.5 
perimeter_ze 
0 15 
0 400 
smoas_30 
0.005 
0.00 0.14 
cornperchress_30 
0.4 
Octy_sc 
0.0 
Concave pa 
se 
Syndy_30 
0.01 
III 
acital dimension 
0.000 
0.5 
2.0 
0 
5 
15 
0.005 
0.025 
0.0 
0.2 
0.4 
0.01 
0.05 
Worst group 
20 
40 
1000 
4000 
0.0 0.4 0.8 
0.00 0.15 0.30 
0.05 
0.15 
radius_warsi 
10 30 
20 50 
texture_worst 
250 
primetter_was 
50 
1000 
0.10 
1.0 
VIINIINIT 
pornpiciness_wars 
0.0 
போர் கப் 
1.2 TUTTI 
0.0 
08'0 000 
IT S 
Sy was 
0.2 
El dimension 
0.05 
10 20 30 
50 
150 
250 
0.10 
0.20 
0.0 
0.6 
1.2 
0.2 
0.4 0.6 
The main conclusions based on plots are: 
• 
Radius's, Perimeter's, and Area's parameters (mean, worst, se) are very strongly correlated with each other in all 3 groups; Concave.point and Concavity are significantly correlated with Radius, Perimeter, and Area in Mean group; Concave.points is somewhat correlated with Concavity, Compactness, and Smoothness in the Mean group; In SE group, there are significantly correlations between the Radius, Perimeter, and Area, and between Concavity, Compactness, and Fractal Dimension; Worst group is similar to Mean group in terms of variable relationships, but has somewhat weaker correlations; The weakest correlations are in SE group, probably because non-linear relationships among variables seem to be more present in it. 
The correlation matrix providing more quantitative insight is present in the R markdown file. 
Is there significant difference between Malignant and Benign? 
The primarily goal is to We want to see if the data is normally distributed, we create the chi-squared plot for all 30 variables. This shows that the data is not distributed normally. 
x2 Plot 
300 
sample quantiles 
100 
- 
- 
- 
- 
- 
- 
0 
20 
30 
40 
50 
theoretical quantiles 
Since both mean and worst mean are correlated we can test only the worst mean. Interested in variables 21 to 30, or the worst means. 
x? Plot 
sample quantiles 
10 20 30 40 
0 
0 
2 
4 
6 
8 
10 
12 
14 
theoretical quantiles 
This is a density plot to assess if the data is normally distributed. These plots include all 10 observations. We can see that the data is not normally distributed to apply MANOVA, however, MANOVA is not sensitive to moderate deviations from normality. Moreover, density plots indicate: 
0.125 
0.100 
0.075 
lines 
density 
0.050 - 
0.025 - 
0.000 
-50 
dens 
Bartlett's test 
Box.M-C 14.070659516 p.value 0.002810534 
#The Bartlett's test determines the covariance matrices are different. 
Can use MANOVA to see if there is a difference between means. These are the results of different tests: 
summary(cancer.m2,test="Wilks") 
Df Wilks approx F num Df den Df Pr(>F) diagnosis 10.33342 565.78 2 566 < 2.2e-16 *** Residuals 567 
Signif. codes: ***** 0.001 **** 0.01 '*0.05 0.1"1 summary(cancer.m2,test="Roy") 
Df Roy approx F num Df den Df Pr(>F) diagnosis 1 1.9992 565.78 2 566 < 2.2e-16 *** Residuals 567 
Signif. codes: 0 ***** 0.001 "**' 0.01 ** 0.05 0.1'' 1 summary(cancer.m2,test="Pillai") 
Df Pillai approx F num Df den Df Pr(>F) diagnosis 10.66658 565.78 2 566 < 2.2e-16 *** Residuals 567 
Signif. codes: 0 ***** 0.001 '**' 0.01 ** 0.05,0.1"' 1 summary(cancer.m2,test="Hotelling-Lawley") 
Df Hotelling-Lawley approx F num Df den Df Pre>F) diagnosis 1 1.9992 565.78 2 566 < 2.2e-16 *** Residuals 567 
T2 test 
[,1] [1.] 850.1412 >qchisq(0.95,2) [1] 5.991465 
The output shows means are different enough to run a model. We run a linear discriminant model, with 30 variables: 
BM B 352 5 M 10 202 
Model 1: This gives a model error of 3.5% 
The issue with this is there are too many variables and the collective data is not normally distributed, so we will use the mean of the worst data. We run a linear discriminant model with the last 10 variables, we omit variables x23,x34 since they are correlated with X21. 
BM B 348 9 M 13 199 
Model 2: This gives a model error of 3.86%. 
By utilizing the PCA we can see that two of the principle components out of 10 are responsible for the most variation. Analysing the proportion of variance represented by the model for last 10 variables, worst means. 
Importance of components: 
PC1 PC2 PC3 PC4 PC5 PC6 Standard deviation 2.3869 1.4443 0.89597 0.73531 0.71741 0.42862 Proportion of Variance 0.5697 0.2086 0.08028 0.05407 0.05147 0.01837 Cumulative Proportion 0.5697 0.7783 0.85860 0.91267 0.96413 0.98251 
PC7 
PC8 
PC9 
PC10 Standard deviation 
0.28959 0.26802 0.12343 0.06326 Proportion of Variance 0.00839 0.00718 0.00152 0.00040 Cumulative Proportion 0.99089 0.99808 0.99960 1.00000 
PC2 
-6 -2 246 
PC1 
This graph displays the separation of the cluster for benign data (red) and malignant data (black) with a 2D projection provided from the 1st principal component and the 2nd principal component From this PCA we can utilize two variables, x21 and x30 to represent most of the model. This could be useful for cost minimization since, only two aspects needs to be analyzed. 
B M B 344 13 M 21 191 
Model 3: This gives a error of 6%. 
Conclusion: If the goal of the model is to have the most accurate prediction then model 2 has to be utilized where 13 incidences has been falsely labeled Benign. If the goal for the model is to minimize the number of variables used and maximize the accuracy by finding values that are linearly independent and contribute to the most variation in the model, we can use model 3, which utilizes x21 and X30, which is radius_worst and fractal_dimension_worst. This is useful for low budget testing, where the extra variables contribute to excess cost. 
We can see the differences in the two variables: 
grp1 grp2 diff.samp.means lower.Cl upper.Cl variable radius_worst 1 2 5.316306 4.722 5.91 
1 grp1 grp2 diff.samp.means lower.Cl upper.CI fractal_dimension_worst 1 2 3.690144 3.687 3.693 
Partition Plot 
app. error rate: 0.058 
35 
м. 
"M 
м M 
L 
M 
M 
M 
30 
мм 
м 
- 
M M M 
M 
M 
мм 
M 
M 
25 
M 
M 
| 
M M M MMMMMM. M M M M M M MM MM 
и им имм 
in 
radius_worst 
м M 
1 мм мм мм мм ммм... ммм 
In 
M 
M 
M MMM 
M 
20 
..MMMMMM M M MMMMMMMMMMMMMM 
мм & MBMM MMMMMMMMMMMM.. 
MMMMM MMMMM 
MB NU 
1 мм 
M 
| в в мень всем, мм мм и 
M 
M 
M 
M 
. 
M 
15 
M 
more 
DO 
FOTO 
B 
B 
10 
man 
B B 
B 
B B 
B 
в 
0.06 
0.08 
0.10 
0.12 
0.12 
0.14 
0.14 
R 
0.16 
0.16 
0.18 
0.20 
fractal_dimension_worst 
Partition plot for the final model of breast cancer data, which displays the separation between the two groups by comparing the radius_worst and fractal_dimension_worst, the most important two variables. As benign tumors tend to have having smaller radius and fractal dimension for the worst three tumors than malignant, the red texts indicate the misclassification. 
Additional Analysis(not used): 
Type of random forest: classification Number of trees: 500 No. of variables tried at each split: 5 
OOB estimate of error rate: 4.46% Confusion matrix: 
B M class.error B 218 6 0.02678571 M 10 125 0.07407407 
Testings to see which is important importance(cancer) 
B M MeanDecreaseAccuracy radius_mean 8.006872 4.77097860 8.777788 texture_mean 6.815259 8.91207982 10.953701 perimeter_mean 7.497765 5.41951779 8.686261 area_mean 9.351406 5.33327446 10.283868 smoothness_mean 0.204728 3.80620374 3.024004 compactness mean 4.409269 4.67482190 6.477738 concavity_mean 7.895892 6.44604873 10.349876 concave.points_mean 7.962426 7.82178852 11.296373 symmetry_mean 2.382605 3.50525705 
4.241900 fractal_dimension_mean 2.706644 0.79044459 2.497193 radius_se 
8.637913 6.81212257 10.647623 texture_se 
3.261479 0.36038849 2.851025 perimeter_se 8.492756 6.75070821 11.070917 area_se 
13.080452 8.65487547 15.830926 smoothness_se 1.013200 1.38387649 1.668194 compactness_se 1.600660 2.85399497 3.433438 concavity_se 3.281035 3.94036986 5.008490 concave.points_se 3.488897 2.64603743 4.467465 symmetry_se 
1.730892 -0.06919739 
1.598386 fractal_dimension_se 1.847817 2.06529453 2.837311 radius_worst 13.537198 10.24510028 15.986024 texture_worst 6.530503 9.37233069 10.179574 perimeter_worst 11.805194 9.78660079 14.285850 area_worst 14.579430 12.25111768 17.502995 smoothness_worst 5.607442 5.26541614 7.555049 compactness_worst 4.591251 5.06143519 6.887224 concavity_worst 7.899224 8.78486214 11.946672 concave.points_worst 13.436160 10.95615399 17.123075 symmetry_worst 5.829468 7.05067402 8.404394 fractal_dimension_worst 1.739782 1.46365578 2.552909 
MeanDecreaseGini radius_mean 
8.7178082 texture_mean 
2.3434321 perimeter_mean 
8.6224273 area_mean 
10.0200592 smoothness_mean 
0.7248869 compactness_mean 
1.8838310 concavity_mean 
6.5047350 concave.points_mean 12.3118219 symmetry_mean 
0.9671528 fractal_dimension_mean 0.6419672 radius_se 
4.1822276 
texture_se 
0.7760996 perimeter_se 
3.1693464 area_se 
11.0966036 smoothness_se 
1.0277929 compactness_se 
0.6090345 concavity_se 
0.7703318 concave.points_se 0.8224412 symmetry_se 
0.7854599 fractal_dimension_se 0.7980390 radius_worst 
17.6148818 texture_worst 
2.7446813 perimeter_worst 
17.8151385 area_worst 
22.5605837 smoothness_worst 1.5348918 compactness_worst 2.7809680 concavity_worst 
4.0025311 concave.points_worst 18.2145946 symmetry_worst 
2.9246894 fractal_dimension_worst 1.1350516 
predValid <- predict(cancer1, test, type = "class") mean(predValid == test$diagnosis) 
0.9571429 table(predValid,test$diagnosis) predValid B M 
B 1284 
M 5 73 varlmpPlot(cancer) 
cancer1 
area_worst concave points worst radius worst area se perimeter worst concavity worst concave.points_mean perimeter se texture_mean radius se concavity_mean area mean texture_worst radius mean perimeter_mean Symmetry_worst smoothness worst compactness_worst compactness mean concavity_se concave points se symmetry_mean compactness se smoothness mean texture se fractal dimension se fractal dimension worst fractal dimension mean smoothness_se Symmetry se 
area_worst concave points_worst perimeter worst radius worst concave points mean area se area mean radius mean perimeter_mean concavity mean radius_se concavity_worst perimeter_se Symmetry_worst compactness_worst texture_worst texture mean compactness mean smoothness worst fractal_dimension_worst smoothness se Symmetry_mean concave.points se fractal dimension_se symmetry_se texture_se concavity se smoothness mean fractal_dimension_mean compactness se 
OOOOO 
15 
07 
20 
10 
15 
MeanDecreaseGini 
MeanDecreaseAccuracy 
gmm = Mclust(cancer[,3:12], 2) table(gmm$classification) 
1 2 223 346 
km = kmeans(cancer[,3:12],2) table(km$cluster) 
1 2 445 124 
