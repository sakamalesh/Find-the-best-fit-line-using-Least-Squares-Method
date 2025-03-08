# Implementation of Univariate Linear Regression
## AIM:
To implement univariate Linear Regression to fit a straight line using least squares.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Get the independent variable X and dependent variable Y.
2. Calculate the mean of the X -values and the mean of the Y -values.
3. Find the slope m of the line of best fit using the formula. 
<img width="231" alt="image" src="https://user-images.githubusercontent.com/93026020/192078527-b3b5ee3e-992f-46c4-865b-3b7ce4ac54ad.png">
4. Compute the y -intercept of the line by using the formula:
<img width="148" alt="image" src="https://user-images.githubusercontent.com/93026020/192078545-79d70b90-7e9d-4b85-9f8b-9d7548a4c5a4.png">
5. Use the slope m and the y -intercept to form the equation of the line.
6. Obtain the straight line equation Y=mX+b and plot the scatterplot.

## Program:
```
/*
Program to implement univariate Linear Regression to fit a straight line using least squares.
Developed by: 
RegisterNumber:

import matplotlib.pyplot as plt
import numpy as np

def calculate_linear_regression(X_str, Y_str):
    
    try:
        X = np.array(list(map(float, X_str.split(','))))
        Y = np.array(list(map(float, Y_str.split(','))))

        # Calculate means
        X_mean = np.mean(X)
        Y_mean = np.mean(Y)

        # Calculate slope (m)
        numerator = np.sum((X - X_mean) * (Y - Y_mean))
        denominator = np.sum((X - X_mean) ** 2)
        m = numerator / denominator

        # Calculate y-intercept (b)
        b = Y_mean - m * X_mean

        # Equation of the line
        print(f"Y = {m:.2f}X + {b:.2f}")

        # Plot scatterplot and line of best fit
        plt.scatter(X, Y)
        plt.plot(X, m * X + b, color='red')
        plt.xlabel("X")
        plt.ylabel("Y")
        plt.title("Linear Regression")
        plt.grid(True)
        plt.show()

        # Calculate errors
        predicted_Y = m * X + b
        errors = Y - predicted_Y

        # Sort errors
        sorted_errors = np.sort(errors)
        return sorted_errors

    except ValueError:
        print("Invalid input format. Please enter comma-separated numbers.")
        return None
    except ZeroDivisionError:
        print("Cannot calculate linear regression when the variance of X is zero.")
        return None

# Get input from the user
X_input = input("Enter X values (comma-separated): ")
Y_input = input("Enter Y values (comma-separated): ")

sorted_errors = calculate_linear_regression(X_input, Y_input)

if sorted_errors is not None:
    print("Sorted Errors:", sorted_errors)
*/

```

## Output:
![best fit line](sam.png)


## Result:
Thus the univariate Linear Regression was implemented to fit a straight line using least squares using python programming.
