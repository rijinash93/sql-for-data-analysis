# sql-for-data-analysis

select * from retail;

SELECT *
FROM retail
WHERE gender = 'Male';


SELECT total_sale
FROM retail
ORDER BY category DESC

SELECT COUNT(*) AS beauty_count
FROM retail
WHERE category = 'Beauty';

select AVG(total_sale) as total_sale_Avg from retail 

select br.manager_id,emp.emp_name
from branch br inner join employee emp
on br.branch_id=emp.branch_id

select *
from branch br left join employee emp
on br.branch_id=emp.branch_id

select *
from branch br right join employee emp
on br.branch_id=emp.branch_id


CREATE VIEW category_sales_summary AS
SELECT category,
       SUM(total_sale) AS total_sales,
       AVG(total_sale) AS avg_sales,
       COUNT(*) AS total_orders
FROM retail
GROUP BY category;


SELECT * FROM category_sales_summary;
