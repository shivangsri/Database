------------------------Creating product table-----------------------------

create table product(
id int(5),
name varchar(100),
email varchar(100));


select * from product;

insert into product(id,name,email)
values
(1,"rohan","rohan@1"),
(2,"shubham","shubham@1"),
(4,"sham","sham@1"),
(5,"mohan","mohan@1");

update product set id=4,name="ram",email="ram@1" where id=4;

select * from product;
select * from product where id>2;



update product set id=5,name="shiva",email="rohan" where id=1;


select * from product where name=""or 1=1;---------------SQL INJECTION

delete from product where id=5;
insert into product(id,name) values (3,"rohn");
select * from product;


---------------------------- Creating Views---------------------------------
create view v1 as
select name,email
from product
where id>1;

select * from v1;

-----------------------------------Using Top/Limit function-------------------
select * from product
limit 2;

select max(id) from product;//---------max function

select avg(id) from product;//--------avg function

select name,email
from product
where name like 'r%';


-----------------------------Creating testing table----------------------------
create table testing(
id int,
name varchar(100),
phone bigint(10));


insert into testing(id,name,phone)
values
(2,"mohan",8800373641),
(3,"sohan",8900373641),
(5,"dohan",9800373641),
(7,"mina",8888373641);

select max(salay) from employee;

select* from testing;


select product.name, testing.name, product.email,testing.phone
from product
left JOIN testing on product.id=testing.id
where product.name like "[m,r]%";


select * from testing
where phone=(select max(phone) from testing);//--------selecting all rows where phone number is max-----//




----------------------------------Creating table OrderData----------------------------
create table OrderData(
OrderID int,
CustomerID int,
OrderDate varchar(100));

insert into OrderData(OrderID,CustomerID,OrderDate)
values
(10308, 2,	"1996-09-18"),
(10309,	37,	"1996-09-19"),
(10310,	77	,"1996-09-20");




--------------------------Creating table Customer-----------------------------------
create table Customer(
CustomerID int,
CustomerName varchar(100),
Country varchar(100));

insert into Customer(CustomerID,CustomerName,Country)
values
(1,"Shivang","India"),
(2,"Sam","USA"),
(3,"Tom","Berlin");



------------------------------------Group By----------------------------------
SELECT COUNT(CustomerID), Country
FROM Customer
GROUP BY Country
ORDER BY COUNT(CustomerID) DESC;




----------------------------------Inner Join between table Customer and OrderData------------------------------

select OrderData.OrderID, OrderData.OrderDate, Customer.CustomerName, Customer.Country
from OrderData
INNER JOIN
Customer  on OrderData.CustomerID=Customer.CustomerID;




----------------------------------Left Join between table Customer and OrderData------------------------------

select OrderData.OrderID, OrderData.OrderDate, Customer.CustomerName, Customer.Country
from OrderData
Left JOIN
Customer  on OrderData.CustomerID=Customer.CustomerID;




----------------------------------Right Join between table Customer and OrderData------------------------------

select OrderData.OrderID, OrderData.OrderDate, Customer.CustomerName, Customer.Country
from OrderData
right JOIN
Customer  on OrderData.CustomerID=Customer.CustomerID;




------------------------------selecting customer name who has max customer id-------------------------------

select CustomerName from Customer
where CustomerID=(select max(CustomerID) from Customer);






-----------------------------------------------------AUTO INCREMENT--------------------------------------------------

CREATE TABLE Persons (
Personid int NOT NULL AUTO_INCREMENT,
LastName varchar(255) NOT NULL,
FirstName varchar(255),
Age int,
   PRIMARY KEY (Personid)
 );
 
 
insert into product(id,name,email) values (98,"shs","sssd");
create view v as
select  *from product where id>10;
create view v1 as
 select name,email
from product where id>4;

 create or replace view v1 as
 select * from product
 where id>4;
select * from v1;






















 











