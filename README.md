# CYF-SQL-Bolt

Link to the coursework
https://sqlbolt.com/

1.1
SELECT title FROM movies;

1.2
SELECT director FROM movies;

1.3
SELECT title, director FROM movies;

1.4
SELECT title, year FROM movies;

1.5
SELECT * FROM movies;

2.1
SELECT title
FROM movies
WHERE id = 6;

2.2
SELECT title
FROM movies
WHERE year
BETWEEN 2000 AND 2010;

2.3
SELECT title
FROM movies
WHERE year
NOT BETWEEN 2000 AND 2010;

2.4
SELECT title, year
FROM movies
WHERE year
LIMIT 5;

3.1
SELECT title
FROM movies
WHERE title
LIKE "Toy Story%";

3.2
SELECT title
FROM movies
WHERE director
LIKE "John Lasseter";

3.3
SELECT title
FROM movies
WHERE director
NOT LIKE "John Lasseter";

3.4
SELECT title
FROM movies
WHERE title
LIKE "WALL-%";


4.1
SELECT DISTINCT director
FROM movies
ORDER BY director ASC;

4.2
SELECT title, year FROM movies
ORDER BY year desc
LIMIT 4;

4.3
SELECT title, year FROM movies
ORDER BY title asc
LIMIT 5;

4.4
SELECT title, year FROM movies
ORDER BY title asc
LIMIT 5 OFFSET 5;

5.1
SELECT city, country, population
FROM north_american_cities
WHERE country = 'Canada';

5.2
SELECT city, country, latitude
FROM north_american_cities
WHERE country = 'United States'
ORDER BY latitude DESC;
 
5.3
SELECT country, city, longitude FROM North_american_cities
Where longitude < -87.629798
ORDER BY longitude ASC;

5.4
SELECT country, city, population FROM North_american_cities
Where country = 'Mexico'
ORDER BY population DESC
LIMIT 2;

5.5
SELECT country, city, population FROM North_american_cities
Where country = 'United States'
ORDER BY population DESC
LIMIT 2 Offset 2;

6.1
SELECT id, title, domestic_sales, international_sales
FROM movies
INNER JOIN boxoffice
ON movies.id = boxoffice.movie_id
ORDER BY id;

6.2
SELECT id, title, domestic_sales, international_sales
FROM movies
INNER JOIN boxoffice
ON movies.id = boxoffice.movie_id
WHERE international_sales > domestic_sales
ORDER BY id;

6.3
SELECT id, title, rating
FROM movies
INNER JOIN boxoffice
ON movies.id = box-office.movie_id
ORDER BY rating DESC;

7.1
SELECT DISTINCT building
FROM employees;

7.2
SELECT building_name, capacity
FROM buildings;

7.3
This is my solution with aliases
SELECT DISTINCT building_name, role
FROM buildings b
LEFT JOIN employees e
ON b.building_name = e.building;

Same solution and no aliases
SELECT DISTINCT building_name, role
FROM buildings
LEFT JOIN employees
ON buildings.building_name = employees.building;

8.1
SELECT name, role 
FROM employees
WHERE building IS NULL;

8.2
SELECT building_name, name
FROM buildings
LEFT JOIN employees
ON buildings.building_name = employees.building
WHERE name IS NULL
