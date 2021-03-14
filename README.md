# Principal_Component_Analysis

Dimensionality Reduction Methods

Proposal of Question

Through a principal component analysis (PCA), what variables may be reduced to focus the results within the dataset as they pertain to the target variable churn?

Defined Goal

The goal of the analysis is to provide a report and justification for dataset dimension reduction. 

Explanation of PCA

Principal component analysis determines which of a dataset’s dependent variables associate with a target variable by accounting for component variance. It relies primarily on the statistical measure, Pearson Correlation Coefficients which measures Eigenvalues and dimensional space, ‘k’. The process eliminates redundancies within the data by eradicating like variables. Programmatically, this is accomplished through the sklearn decomposition package. After the data is normalized, the numerical variables’ Eigenvalues and Eigenvectors will be discovered. Then, through a scree plot the number of variable redundancies will be visually and quantitatively displayed via plot and array.

Theoretically explained, this analysis begins with a chosen dataset with many variables and components. It then breaks up these many components and reduces their dimensionality to produce the variable Eigenvectors and Eigenvalues. These Eigenvectors and Eigenvalues are a representation of dimensional space which we will call ‘k’. That space ‘k’ accounts for the variance and covariance of each component. Then, this accounting of variance allows for model reduction. Each components’ Eigenvalue ought to add to 1 or greater, while a total of those chosen (reduced) variables should account for at least 90% (or .90) of your variance. In example, take a dataset with ten numerical continuous variables. These are then broken into components, standardized, and then divided over the sum of their variance. This allows for a perfect accounting for variance throughout your components. Following the example of the ten variables, let us assume that the result of the above process proves that the first two components account for 90% (or .90) of the total variance. These two first variables would then be considered principal components and the other eight variables would be dropped. Thus, PCA is called a dimensionality reduction method for exploratory analysis. A new reduced dataset would then be formed for future, more accurate, modelling. 	
The expected outcome of this project is a complete list and visual representation of variances regarding variable redundancy as well as known principal components. Thus, leading to the implications of eliminating irrelevant data aiding in strategic management initiatives and predictive modelling.  

PCA Assumption

The principal component analysis assumes that the data being fitted is numeric, continuous, and that there are no significant outliers. Mitigating these assumptions, numeric variables will be used, and others transformed to numeric when appropriate. Furthermore, the data will be standardized to fit the Pearson Correlation Coefficient requirements for this analysis.


Continuous Dataset Variables

Continuous data is data which can be broken down to a float and still make sense in a count or measurement. For example, it is nonsensical to have 2.5 children; therefore, the count of children is not continuous. Temperature is a perfect example of a continuous data type as 4.5 degrees Celsius is plausible. Those pieces of the dataset which are to be analyzed are: age, income, outage seconds per-week, yearly equipment failure, tenure, monthly charge, and bandwidth GB per year.

Standardization of Dataset Variables

The standardized dataset variables have been submitted via an Excel document alongside this submission. 
Principal Components
When performing a principal component analysis, both variance and covariance are used in the process. These matrixes are used to determine an Eigenvalue and Eigenvector. Allowing for a perception of variance composition throughout the different variables. Below are the variance and covariance matrix for each of the principal components. 
Variance PCA Matrix
array([[ 0.72092524, -0.39877774, -0.6799776 ,  0.9466579 , -1.04874621,
        -0.00394256, -1.13848703],
       [-1.25995716, -0.64195445,  0.57033109,  0.9466579 , -1.26200116,
         1.6303259 , -1.18587584],
       [-0.14873045, -1.07088496,  0.25234705,  0.9466579 , -0.7099398 ,
        -0.29522482, -0.61213775],
       [-0.24535886, -0.74052492,  1.65050585, -0.62586353, -0.65952396,
        -1.22652107, -0.56185715],
       [ 1.44563831,  0.00947792, -0.62315605,  0.9466579 , -1.2425512 ,
        -0.5280857 , -1.42818447],
       [ 1.44563831, -0.60807216, -0.5312245 ,  0.9466579 , -1.04097514,
         0.28836988, -1.07678889],
       [ 1.25238149, -1.00499743,  0.39681714,  0.9466579 , -0.80514421,
         0.64026766, -0.67962126],
       [-1.11501455, -0.46269425, -0.74271242, -0.62586353, -1.14447583,
        -1.34309826, -1.10412995]])

Covariance PCA Matrix
array([[ 1.00010001, -0.00409101, -0.00804752,  0.00857821,  0.01698097,
         0.01072958, -0.01472512],
       [-0.00409101,  1.00010001, -0.01001155,  0.00542382,  0.00211458,
        -0.00301427,  0.00367392],
       [-0.00804752, -0.01001155,  1.00010001,  0.00290902,  0.00293225,
         0.02049812,  0.00417608],
       [ 0.00857821,  0.00542382,  0.00290902,  1.00010001,  0.01243615,
        -0.00717299,  0.0120349 ],
       [ 0.01698097,  0.00211458,  0.00293225,  0.01243615,  1.00010001,
        -0.00333714,  0.99159435],
       [ 0.01072958, -0.00301427,  0.02049812, -0.00717299, -0.00333714,
         1.00010001,  0.06041247],
       [-0.01472512,  0.00367392,  0.00417608,  0.0120349 ,  0.99159435,
         0.06041247,  1.00010001]])

Identification of Total Number of Components

The Kaiser Criterion was used in this analysis to determine the dataset’s principal components. The Kaiser Criterion eliminates those components with an Eigenvalue lesser than one. Further, it classifies those with Eigenvalues greater than 1 as a principal component to reduce the model. A Scree plot is a graph of all components’ Eigenvalues allowing for a visual exploration of Eigenvalues. Scree plots turn a 4-dimensional representation of variables into a 2-dimensional visual. This dimensional reduction permits the human mind to understand the 4-dimensional relationship whereas it was inconceivable before the visual. These tools together allow for the reduction of a dataset to increase model accuracy for future analysis. In summary, those values with Eigenvalues greater than 1 will be kept.
The corresponding Eigenvalues rounded for each component are age at 0.0059, income at 1.9936, outage seconds per-week at 0.9684, yearly equipment failure at 1.0253, tenure at 1.0095, monthly charge at 1.0007, bandwidth at 0.9971. Following the Kaiser Criterion, the dropped variables will be age, outage seconds per-week, and bandwidth. The reduced dataset with those components to be kept will contain income, yearly equipment failure, tenure, and monthly charge. The Eigenvalues for each component and Scree plot is captured below via screenshot.

Total Number of Principal Components and Justification

The total number of components to be kept as principal components is 4. The justification of this total number of principal components lies in their individual and collective assessment. Individually, the components were measured with the Kaiser Criterion. Those components with Eigenvalues greater than 1 became principal components. Collectively, the reduction is justified by the ratio of covariance accounted for. The covariance was assessed programmatically to show how much total variance each component accounted for. Prior to reduction, total variance accounted for by the selected variables is 71.84%. Below, there is a screenshot provided of the code for the Scree plot and Eigenvalues. 

Total Variance of Components

The variance prior to model reduction accounted for by only those principal components is shown in the table below.

Principal Component (Full Model)	Variance Accounted For (Full Model)
Income	0.28478
Yearly Equipment Failure	0.14646
Tenure	0.14420
Monthly Charge	0.14295
Total Variance Accounted For:	0.7184

The variance accounted for by each principal component after the reduction of the model is shown in the table below. It is clear, that the variance is nearly evenly split amongst components suggesting equal contribution to the dataset’s covariance. 

Principal Component (Reduced Model)	Variance Accounted For (Reduced Model)
Income	0.2545
Yearly Equipment Failure	0.2466
Tenure	0.2496
Monthly Charge	0.2491
Total Variance Accounted For:	0.9999

Total Variance Captured by Components

The total variance captured by the components in this analysis is 0.7184 or 72%. The principal components were selected based on their Eigenvalues being greater than 1. The sum of those chosen components variance is then computed to determine the ‘Total Variance Captured by Components’ which is 0.7184 or 72%. This means that the principal components account for about 72% of the total variance throughout all components within the dataset making them principal components. A screenshot of the code used to compute this as well as its result is below.

Summary of Data Analysis

In summary, the analysis performed answered the research question and achieved the project goal. The question being, “Through a principal component analysis (PCA), what variables may be reduced to focus the results within the dataset as they pertain to the target variable churn?” Those variables to discarded are age, outage seconds per-week, and bandwidth. The method used to determine their ineligibility for principal component was determined the Kaiser Criterion. Those with Eigenvalues lower than 1 were dropped, and those with Eigenvalues lesser than 1 were kept. The goal of the project was, “. . . to provide a report and justification for dataset dimension reduction”. The reduction has been justified through quantitative reasoning (Keiser Criterion) as well as through visualization (Scree plot). The number of principal components being four namely, income, tenure, yearly equipment failure, and monthly charge. 
	
The steps for the analysis were:

1.	Import Packages and the Dataset
2.	Standardize the Numeric/Continuous Variables
3.	Discover and Display the Variance and Covariance Matrixes for the Dataset
4.	Discover and Display the Eigenvalues and Eigenvectors
5.	Calculate the Variance per Principal Component
6.	Visualize a Scree Plot
7.	Reduce the Dataset
8.	Repeat Pre-processing steps 2-5
9.	Display the Reduced Model’s Covariance’s per component

Through this principal component analysis, the company now has the capability of more accurately predicting customer churn while using predictive modelling. This report will assist strategic management initiatives in the effort to reduce and eliminate customer churn.
