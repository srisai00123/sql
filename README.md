# SQL 

## Creating and Inserting the Data 

### Creting a table names department 

CREATE TABLE Departments (
  Code INTEGER PRIMARY KEY,
  Name varchar(255) NOT NULL ,
  Budget decimal NOT NULL 
);

### Creating a table named Employees

CREATE TABLE Employees (
  SSN INTEGER PRIMARY KEY,
  Name varchar(255) NOT NULL ,
  LastName varchar(255) NOT NULL ,
  Department INTEGER NOT NULL
);


### Inserting values into the Department table

INSERT INTO Departments(Code,Name,Budget) VALUES(14,'IT',65000);
INSERT INTO Departments(Code,Name,Budget) VALUES(37,'Accounting',15000);
INSERT INTO Departments(Code,Name,Budget) VALUES(59,'Human Resources',240000);
INSERT INTO Departments(Code,Name,Budget) VALUES(77,'Research',55000);


### Inserting the values into the Employees Table

INSERT INTO Employees(SSN,Name,LastName,Department) VALUES('123234877','Michael','Rogers',14);
INSERT INTO Employees(SSN,Name,LastName,Department) VALUES('152934485','Anand','Manikutty',14);
INSERT INTO Employees(SSN,Name,LastName,Department) VALUES('222364883','Carol','Smith',37);
INSERT INTO Employees(SSN,Name,LastName,Department) VALUES('326587417','Joe','Stevens',37);
INSERT INTO Employees(SSN,Name,LastName,Department) VALUES('332154719','Mary-Anne','Foster',14);
INSERT INTO Employees(SSN,Name,LastName,Department) VALUES('332569843','George','ODonnell',77);
INSERT INTO Employees(SSN,Name,LastName,Department) VALUES('546523478','John','Doe',59);
INSERT INTO Employees(SSN,Name,LastName,Department) VALUES('631231482','David','Smith',77);
INSERT INTO Employees(SSN,Name,LastName,Department) VALUES('654873219','Zacary','Efron',59);
INSERT INTO Employees(SSN,Name,LastName,Department) VALUES('745685214','Eric','Goldsmith',59);
INSERT INTO Employees(SSN,Name,LastName,Department) VALUES('845657245','Elizabeth','Doe',14);
INSERT INTO Employees(SSN,Name,LastName,Department) VALUES('845657246','Kumar','Swamy',14);

## Select Queries 

### Selecting all the data from the employees table

SELECT * FROM EMPLOYEES;


### Select the last name of all employees.

SELECT LASTNAME FROM EMPLOYEES;

### Select the last name of all employees, without duplicates.

SELECT DISTINCT LASTNAME FROM EMPLOYEES;

### Select all the data of employees whose last name is "Smith".

SELECT * FROM EMPLOYEES WHERE LastName = 'Smith';

### Select all the data of employees whose last name is "Smith" or "Doe".

SELECT * FROM EMPLOYEES WHERE LastName IN ('Smith','Doe');

### Select all the data of employees that work in department 14.

SELECT * FROM EMPLOYEES WHERE DEPARTMENT=14;

###  Select all the data of employees that work in department 37 or department 77.

SELECT * FROM EMPLOYEES WHERE DEPARTMENT IN (37,77);

### Select all the data of employees whose last name begins with an "S".

SELECT * FROM EMPLOYEES WHERE LastName like 'S%';

### Select the sum of all the departments' budgets.

SELECT sum(BUDGET) AS Department_Budget FROM Departments;

### Select the number of employees in each department (you only need to show the department code and the number of employees)

select Department, count(*) from employees group by department;

## JOINS

### Select all the data of employees, including each employee's department's data.

SELECT SSN,E.NAME,E.LASTNAME,E.DEPARTMENT,D.CODE,D.NAME,D.BUDGET FROM EMPLOYEES E INNER JOIN DEPARTMENTS D ON E.DEPARTMENT=D.CODE;
 
 ### Select the name and last name of each employee, along with the name and budget of the employee's department.
 SELECT E.NAME,E.LASTNAME,D.NAME,D.BUDGET FROM EMPLOYEES E JOIN DEPARTMENTS D ON E.DEPARTMENT=D.CODE;
 
