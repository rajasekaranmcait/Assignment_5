
Assignment - 5:
SQL_Query

CREATE a DATABASE for Employee.

CREATE a TABLE for an Organisation.

To find the manager and sub-ordinates for given employee.

QUESTIONS:

Question-1: Find all the sub-ordinates for a given employee :

select * from Organisation where Desig='staff' and ReportTo = (select EmpId from Organisation where Name='Kohli');

| EmpId |   Name | Desig |             Mail | ReportTo |
|-------|--------|-------|------------------|----------|
|     4 | Ashwin | Staff | ashwin@gmail.com |        3 |
|     5 | Jadeja | Staff | jadeja@gmail.com |        3 |

Question-2: Find the manager of an employee :

select * from Organisation where Desig = 'Manager' and EmpId = (select ReportTo as EmpId FROM Organisation WHERE Name= 'Kohli');

| EmpId |  Name |   Desig |            Mail | ReportTo |
|-------|-------|---------|-----------------|----------|
|     1 | Dhoni | Manager | dhoni@gmail.com |          |
