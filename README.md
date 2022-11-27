# Clothes-Shop-Backend

<h3>Introduction</h3>

You can import database from `./database/clothes_shop.sql` in your device. But if your device does not already have MySQL and phpMyAdmin,
you can follow the instructions at the bottom to install them using Docker.

<h3>Install the Docker MySQL and phpMyAdmin Container</h3>

<ul>
<li>

<strong>Pull image</strong>
<p><a href="https://hub.docker.com/_/mysql">MySQL Docker Image</a></p>

```
docker pull mysql
```
<p><a href="https://hub.docker.com/_/phpmyadmin">phpMyAdmin Docker Image</a></p>

```
docker pull phpmyadmin
```
</li>
<li>

<strong>Run the container</strong>

```
docker run --name MySQL -e MYSQL_ROOT_PASSWORD=123456 -d mysql
```

```
docker run --name phpMyAdmin -d --link MySQL:db -p 8080:80 phpmyadmin
```
</li>
<li>

<strong>Create a database</strong>

```
docker exec -it MySQL bash
```

```
mysql -u root -p
```

```
CREATE DATABASE clothes_shop;
```
</li>
<li>
<strong>Import a database table</strong>
 
open `http://localhost:8080` and choose a `clothes_shop` database from our created in the preceding, import `clothes_shop.sql` from `./database`
</li>

</ul>
