# Exercise 01: World Database SQL Practice

- Name: Venkat Teja Nallamothu
- Course: Database for Analytics
- Module: 1
- Database Used: World Database

---

## Instructions

- Answer each question below.
- All SQL commands **must be executed** against the World database.
- For each SQL command:
  - Include the SQL in a fenced code block
  - Include a **screenshot** showing the command and results
- Store screenshots in the `screenshots/` folder and embed them below each answer.

---

## Question 1

**Compare and contrast the data types used for:**
- `country.Population`
- `country.LifeExpectancy`

Why were these data types selected?

### Answer
_The Population is of 'int' data type with default values as 0 and its not nullable NO_
_The LifeExpectancy is of 'decimal(3,1)' data type with default values NULL and is nullable_

### Screenshot
_Show the table structure or DESCRIBE output._

```sql
DESCRIBE country;
```

![E1 Screenshot](screenshots/e1/q1.png)

---

## Question 2

**What is the data type of `country.IndepYear`?**
Why do you think this data type was selected?

### Answer
_IndepYear is of type smallint so the Storage Size for INT = 4 bytes while SMALLINT = 2 bytes so this makes it significantly reduction in wasted space on disk. And as it is only showing year a small datatype is suffitient_

### Screenshot

```sql
DESCRIBE country;
```

![Q2 Screenshot](screenshots/e1/q2.png)

---

## Question 3

**Make a case for a different data type for `country.IndepYear`.**
Explain why your proposed data type might be better in some situations.

### Answer
_I would say YEAR(4) is a better datatype as it has a range of 1901 … 2155 and it’s compact and semantically clear._

---

## Question 4

Write a SQL command to **list the names of all cities in alphabetical order**.

### SQL

```sql
SELECT Name
FROM city
ORDER BY Name;
```

### Screenshot

![Q4 Screenshot](screenshots/e1/q4.png)

---

## Question 5

Write a SQL command to **list all forms of government from the `country` table**, showing **each only once**, sorted alphabetically.

### SQL

```sql
SELECT DISTINCT GovernmentForm
FROM country
ORDER BY GovernmentForm;
```

### Screenshot

![Q5 Screenshot](screenshots/e1/q5.png)

---

## Question 6

Write a SQL command to **list all countries in the `Oceania` continent**.

### SQL

```sql
SELECT Name
FROM country
WHERE Continent = 'Oceania';
```

### Screenshot

![Q6 Screenshot](screenshots/e1/q6.png)

---

## Question 7

Write a SQL command to **list the names and country code of all cities**.

### SQL

```sql
SELECT Name, CountryCode
FROM city;
```

### Screenshot

![Q7 Screenshot](screenshots/e1/q7.png)

---

## Question 8

Write a SQL command to **update the city named `"Nashville-Davidson"` to `"Nashville"`**.

### SQL

```sql
UPDATE city
SET Name = 'Nashville'
WHERE Name = 'Nashville-Davidson';
```

### Screenshot

![Q8 Screenshot](screenshots/e1/q8.png)

---

## Question 9

Write a SQL command to **insert a new country named `"Narnia"`** with a country code of `"NAR"`.
Use reasonable values for the remaining columns.

### SQL

```sql
INSERT INTO country (Code, Name, Continent, Region, Population)
VALUES ('NAR', 'Narnia', 'Europe', 'Fantasy', 1000000);
```

### Screenshot

![Q9 Screenshot](screenshots/e1/q9.png)

---

## Question 10

Write a SQL command to **delete the country with the country code `"NAR"`**.

### SQL

```sql
DELETE FROM country
WHERE Code = 'NAR';
```

### Screenshot

![Q10 Screenshot](screenshots/e1/q10.png)
