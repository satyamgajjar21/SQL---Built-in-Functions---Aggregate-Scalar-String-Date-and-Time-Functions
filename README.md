## **Hands-on Lab: Built-in Functions - Aggregate, Scalar, String, Date and Time Functions**

Now let us practice using **sub-queries** and working with **multiple tables**. Use the **PETRESCUE-CREATE.sql** file provided to create the table and execute the queries in the last two videos.

---

## **Objectives**

After completing this lab, you will be able to:

1. **Compose and run sub-queries with multiple tables**
2. **Check query results and view log files**

---

## **Sample Data**

| ID | ANIMAL   | QUANTITY | COST   | RESCUEDATE  |
|----|----------|----------|--------|-------------|
| 1  | Cat      | 9        | 450.09 | 5/29/2018   |
| 2  | Dog      | 3        | 666.66 | 6/1/2018    |
| 3  | Dog      | 1        | 100    | 6/4/2018    |
| 4  | Parrot   | 2        | 50     | 6/4/2018    |
| 5  | Dog      | 1        | 75.75  | 6/10/2018   |
| 6  | Hamster  | 6        | 60.6   | 6/11/2018   |
| 7  | Cat      | 1        | 44.44  | 6/11/2018   |
| 8  | Goldfish | 24       | 48.48  | 6/14/2018   |
| 9  | Dog      | 2        | 222.22 | 6/15/2018   |

---

## **Exercise 1: Create the Pet Rescue Table**

1. **Download** the script file **PETRESCUE-CREATE.sql**  
   *Right-click on the link and choose "Save As..."*

2. **Login** to [IBM Cloud Resources Dashboard](https://cloud.ibm.com/resources)  
   Go to your **Db2 service** and click on **Open Console**.

3. Navigate to **Run SQL** page, click **+ (Add New Script)** → **From File**

4. Locate and open **PETRESCUE-CREATE.sql**

5. Click **Run all** to execute the statements.

6. **Check Results** on the right pane for errors or warnings.

7. To **view tables**, go to **Explore > Tables**

8. Select the **Schema** for your Db2 User ID to see the **PETRESCUE** table.

9. Click a table to view its **schema definition** and **View Data**.

---

## **Exercise 2: Aggregate Functions**

- **Query A1**: Total cost of all animal rescues  
  `SELECT SUM(COST) FROM PETRESCUE;`

- **Query A2**: Total cost with alias  
  `SELECT SUM(COST) AS SUM_OF_COST FROM PETRESCUE;`

- **Query A3**: Maximum quantity of animals rescued  
  `SELECT MAX(QUANTITY) FROM PETRESCUE;`

- **Query A4**: Average cost of animals rescued  
  `SELECT AVG(COST) FROM PETRESCUE;`

- **Query A5**: Average cost of rescuing a dog  
  `SELECT AVG(COST/QUANTITY) FROM PETRESCUE WHERE ANIMAL = 'Dog';`

---

## **Exercise 3: Scalar and String Functions**

- **Query B1**: Rounded cost of each rescue  
  `SELECT ROUND(COST) FROM PETRESCUE;`

- **Query B2**: Length of each animal name  
  `SELECT LENGTH(ANIMAL) FROM PETRESCUE;`

- **Query B3**: Animal names in uppercase  
  `SELECT UCASE(ANIMAL) FROM PETRESCUE;`

- **Query B4**: Unique animal names in uppercase  
  `SELECT DISTINCT UCASE(ANIMAL) FROM PETRESCUE;`

- **Query B5**: All columns where animal is 'cat' (case insensitive)  
  `SELECT * FROM PETRESCUE WHERE LCASE(ANIMAL) = 'cat';`

---

## **Exercise 4: Date and Time Functions**

- **Query C1**: Day of the month when cats were rescued  
  `SELECT DAY(RESCUEDATE) FROM PETRESCUE WHERE ANIMAL = 'Cat';`

- **Query C2**: Number of rescues in May (5th month)  
  `SELECT SUM(QUANTITY) FROM PETRESCUE WHERE MONTH(RESCUEDATE) = '05';`

- **Query C3**: Number of rescues on the 14th day  
  `SELECT SUM(QUANTITY) FROM PETRESCUE WHERE DAY(RESCUEDATE) = '14';`

- **Query C4**: Third day from each rescue  
  `SELECT (RESCUEDATE + 3 DAYS) FROM PETRESCUE;`

- **Query C5**: Days since rescue (today - rescue date)  
  `SELECT (CURRENT DATE - RESCUEDATE) FROM PETRESCUE;`

---

## **Summary**

You can now:

- Compose and run various types of **SQL queries**
- Use **aggregate**, **scalar**, **string**, and **date/time** functions
- Check query results and logs for accuracy

---

## **Author(s)**

**Rav Ahuja**
