# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M4
# IAPR-4- Module 4 - FoC
7. Implementation of Functions.
8. Implementation of passing parameters.
# Ex.No:16
  Implement a C program to read a date in the format DD/MM/YYYY and determine whether the entered date is valid. The program should check the correctness of the day, month, and year, including leap year calculations for February.

## Aim:
 To implement a C program that validates a user-entered date using a function without parameters and without return value, ensuring the correctness of day, month, year, and leap year conditions.
## Algorithm:
Step 1: Start<br>
Step 2: Include the standard input-output library: #include<stdio.h>.<br>
Step 3: Call the function `validateDate()`.<br>
Inside `validateDate()` function:<br>
Step 4: Declare variables `dd`, `mm`, and `yy`.<br>
Step 5: Ask the user to enter a date in `DD/MM/YYYY` format.<br>
Step 6: Read the date values using `scanf`.<br>
Step 7: Check if the year is between **1900 and 9999**.<br>
 - If the year is invalid, display **"Year is not valid"** and stop further checks.<br>
Step 8: Check if the month is between **1 and 12**.<br>
- If the month is invalid, display **"Month is not valid"** and stop further checks.<br>
Step 9: If the month has **31 days**, check if the day is between **1 and 31**.<br>
Step 10: If the month has **30 days**, check if the day is between **1 and 30**.<br>
Step 11: If the month is **February**:<br>
  - Check if the day is between **1 and 28**, or if the day is **29**, verify if it's a **leap year**.<br>
Step 12: If any valid condition is satisfied, display **"Date is valid."**<br>
Step 13: Otherwise, display **"Date is invalid."**<br>
Step 14: Stop<br>
## Program:
```
#include <stdio.h>

void validateDate() {
    int dd, mm, yy;
    printf("Enter date (DD/MM/YYYY): ");
    scanf("%d/%d/%d", &dd, &mm, &yy);

    if (yy < 1900 || yy > 9999) {
        printf("Year is not valid.\n");
        return;
    }
    if (mm < 1 || mm > 12) {
        printf("Month is not valid.\n");
        return;
    }

    // Check days
    if (mm == 1 || mm == 3 || mm == 5 || mm == 7 || mm == 8 || mm == 10 || mm == 12) {
        if (dd >= 1 && dd <= 31) printf("Date is valid.\n");
        else printf("Date is invalid.\n");
    }
    else if (mm == 4 || mm == 6 || mm == 9 || mm == 11) {
        if (dd >= 1 && dd <= 30) printf("Date is valid.\n");
        else printf("Date is invalid.\n");
    }
    else if (mm == 2) {
        if ((yy % 400 == 0) || (yy % 100 != 0 && yy % 4 == 0)) {
            if (dd >= 1 && dd <= 29) printf("Date is valid.\n");
            else printf("Date is invalid.\n");
        } else {
            if (dd >= 1 && dd <= 28) printf("Date is valid.\n");
            else printf("Date is invalid.\n");
        }
    }
}

int main() {
    validateDate();
    return 0;
}
```
## Output:
<img width="376" height="57" alt="image" src="https://github.com/user-attachments/assets/017cf14f-765a-46d1-8def-40d7c46537d5" />

## Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# Ex.No:17
  Develop a C program to read two numbers from the user and determine the maximum and minimum values. Use user-defined functions with arguments and return values—one function to find the maximum (max()) and another to find the minimum (min()).
## Aim:
 To develop a C program that uses functions with parameters and return values to compute and display the maximum and minimum of two user-entered numbers.
## Algorithm:
Step 1: Start<br>
Step 2: Include the standard input-output library: #include<stdio.h>.<br>
Step 3: Declare variables `num1`, `num2`, `maximum`, and `minimum`.<br>
Step 4: Ask the user to enter two numbers.<br>
Step 5: Read the numbers using `scanf`.<br>
Step 6: Call the function `max(num1, num2)`.<br>
Step 7: Inside function `max(num1, num2)`:<br>
- **Step 7.1:** Receive two integer arguments.  <br>
- **Step 7.2:** Compare the two numbers.  <br>
- **Step 7.3:** If `num1 > num2`, return `num1`.  <br>
- **Step 7.4:** Otherwise, return `num2`.<br>
Step 8: Store the returned value in `maximum`.<br>
Step 9: Call the function `min(num1, num2)`.<br>
Step 10: Inside function `min(num1, num2)`:<br>
- **Step 10.1:** Receive two integer arguments.  <br>
- **Step 10.2:** Compare the two numbers.  <br>
- **Step 10.3:** If `num1 > num2`, return `num2`. <br> 
- **Step 10.4:** Otherwise, return `num1`.<br>
Step 11: Store the returned value in `minimum`.<br>
Step 12: Display the returned maximum and minimum values.<br>
Step 13: Stop<br>
## Program:
```
#include <stdio.h>
int max(int a,int b){ return a>b?a:b; }
int min(int a,int b){ return a<b?a:b; }
int main(){
    int x,y;
    scanf("%d%d",&x,&y);
    printf("Max=%d\nMin=%d\n",max(x,y),min(x,y));
    return 0;
}
```
## Output:
<img width="73" height="109" alt="image" src="https://github.com/user-attachments/assets/98de6ecb-a5b9-4cba-bb16-2303b5fba633" />

## Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# Ex.No:18
  Develop a C program to convert temperatures between Celsius and Fahrenheit: Convert Celsius to Fahrenheit using a function that returns the converted value. Convert Fahrenheit to Celsius using another function that returns the converted value. Display the results in the main() function.
## Aim:
 To develop a C program that converts temperatures between Celsius and Fahrenheit using functions with return values.
## Algorithm:
Step 1: Start
Step 2: Include the standard input-output library: #include<stdio.h>.  <br>
Step 3: Declare function prototypes:<br>
 - `float celtof()`;<br>  
 - `float ftocel()`;<br>
Step 4: Enter the `main()` function.<br>
Step 5: Call the `celtof()` function to convert Celsius to Fahrenheit.<br>
Step 6: Inside `celtof()` function:<br>
 - Declare float variables `C` and `F`.  <br>
 - Display the message: **"Enter the temperature in Celsius"**.  <br>
 - Read the value of `C` from the user.  <br>
 - Calculate Fahrenheit using the formula: `F = (C * 9 / 5) + 32`.  <br>
 - Return `F` to `main()`.<br>
Step 7: Print the returned Fahrenheit value in `main()`.<br>
Step 8: Call the `ftocel()` function to convert Fahrenheit to Celsius.<br>
Step 9: Inside `ftocel()` function:<br>
 - Declare float variables `f` and `celsius`.  <br>
 - Display the message: **"Enter the temperature in Fahrenheit"**.  <br>
 - Read the value of `f` from the user.  <br>
 - Calculate Celsius using the formula: `celsius = (f - 32) * 5 / 9`.  <br>
 - Return `celsius` to `main()`.<br>
Step 10: Print the returned Celsius value in `main()`.<br>
Step 11: Stop<br>
## Program:
```
#include <stdio.h>
float celtof(float c){ return (c*9/5)+32; }
float ftocel(float f){ return (f-32)*5/9; }
int main(){
    float c,f;
    scanf("%f%f",&c,&f);
    printf("F=%.2f\nC=%.2f\n",celtof(c),ftocel(f));
    return 0;
}
```
## Output:
<img width="99" height="109" alt="image" src="https://github.com/user-attachments/assets/6b455e3b-72fc-4180-8774-d34f3a4b0675" />

## Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# Ex.No:19
  Build a C program to print the elements of a given 4×4 matrix in spiral order starting from the top-left element and moving clockwise,using a user-defined parameterized function without return spiralPrint().
## Aim:
 To build a C program to display the elements of a 2D array in spiral form, traversing the outer elements first and then moving inward in a clockwise direction, using a user-defined parameterized function without return spiralPrint().
## Algorithm:
Step 1: Start<br>
Step 2: Include the standard input-output library: #include<stdio.h>.  <br>
Step 3: Define constants `R` and `C` for the number of rows and columns in the matrix.<br>
Step 4: Declare a function `spiralPrint(int m, int n, int a[R][C])` to print the matrix in spiral order.<br>
Step 5: Inside `spiralPrint()` function:<br>
 - Initialize variables:  <br>
   - `k = 0` → starting row index  <br>
   - `l = 0` → starting column index  <br>
   - `m` → ending row index  <br>
   - `n` → ending column index  <br>
 - Repeat the following while `k < m` and `l < n`:<br>
   - a. **Print the top row from left to right**:  <br>
     - Loop from column `l` to `n-1` and print `a[k][i]`.  <br>
     - Increment `k`.       <br>
   - b. **Print the last column from top to bottom**:  <br>
     - Loop from row `k` to `m-1` and print `a[i][n-1]`.  <br>
     - Decrement `n`.       <br>
   - c. **If `k < m`, print the bottom row from right to left**:  <br>
     - Loop from column `n-1` to `l` and print `a[m-1][i]`.  <br>
     - Decrement `m`.       <br>
   - d. **If `l < n`, print the first column from bottom to top**:  <br>
     - Loop from row `m-1` to `k` and print `a[i][l]`.  <br>
     - Increment `l`.<br>
Step 6: In the `main()` function:<br>
- Declare and initialize a 4×4 matrix `a`.  <br>
- Call `spiralPrint(R, C, a)` to print the elements in spiral order.<br>
Step 7: Stop<br>
## Program:
```
#include <stdio.h>
void spiralPrint(int m,int n,int a[4][4]){
    int k=0,l=0;
    while(k<m && l<n){
        for(int i=l;i<n;i++) printf("%d ",a[k][i]); k++;
        for(int i=k;i<m;i++) printf("%d ",a[i][n-1]); n--;
        if(k<m){ for(int i=n-1;i>=l;i--) printf("%d ",a[m-1][i]); m--; }
        if(l<n){ for(int i=m-1;i>=k;i--) printf("%d ",a[i][l]); l++; }
    }
}
int main(){
    int a[4][4]={{1,2,3,4},{5,6,7,8},{9,10,11,12},{13,14,15,16}};
    spiralPrint(4,4,a);
    return 0;
}
```
## Output:

<img width="412" height="28" alt="image" src="https://github.com/user-attachments/assets/24e93a85-0106-4fd3-b7f8-d0badb535514" />

## Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# Ex.No:20
  Build a C program to convert a string such that the first and last characters, as well as the characters before and after each space, are converted to uppercase. Implement this using a user-defined parameterized function without return.
## Aim:
To build a C program to convert a string as described above, using a user-defined parameterized function without return convertFirstCLastC(char str[]).
## Algorithm:
Step 1: Start<br>
Step 2: Include the standard input-output library: #include<stdio.h>.  <br>
Step 3: Declare a user-defined void function `convertFirstCLastC(char str[])` that takes the string as a parameter.<br>
Step 4: Inside `convertFirstCLastC(char str[])` function:<br>
 - Find the length of the string `len`.  <br>
 - Convert the first character `str[0]` to uppercase.  <br>
 - Loop through the string from index `1` to `len-2`:  <br>
   - If a character is a space, capitalize the character before and after it.  <br>
 - Convert the last character `str[len-1]` to uppercase.<br>
Step 5: In `main()` function:<br>
 - Declare a string `str[100]`.  <br>
 - Read the input string from the user.  <br>
 - Call the function `convertFirstCLastC(char str[])`.  <br>
 - Print the modified string.<br>
Step 6: Stop<br>
## Program:
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

void convertFirstCLastC(char str[]){
    int len=strlen(str);
    str[0]=toupper(str[0]);
    str[len-1]=toupper(str[len-1]);
    for(int i=1;i<len-1;i++)
        if(str[i]==' '){
            str[i-1]=toupper(str[i-1]);
            str[i+1]=toupper(str[i+1]);
        }
}

int main(){
    char str[100];
    scanf("%[^\n]",str);
    convertFirstCLastC(str);
    printf("%s\n",str);
    return 0;
}
```
## Output:

<img width="66" height="56" alt="image" src="https://github.com/user-attachments/assets/de7e86a7-4c80-4515-8e73-f14ce2c688c3" />

## Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.
