# Desgin-Role-Permission

#### MYSQL 

<b>

```sql

    CREATE TABLE roles (
        id INT AUTO_INCREMENT NOT NULL,
        role_name varchar(200) NOT NULL,
        PRIMARY KEY (id)
    );

    CREATE TABLE users (
        id INT AUTO_INCREMENT NOT NULL,
        username varchar(200) NOT NULL,
        password varchar(200) NOT NULL,
        role_id INT NOT NULL,
        PRIMARY KEY (id),
        FOREIGN KEY (role_id) REFERENCES roles(id)
    );

    CREATE TABLE permissions (
        id INT AUTO_INCREMENT NOT NULL,
        per_code varchar(200) NOT NULL,
        per_name varchar(200) NOT NULL,
        PRIMARY KEY (id)
    );

    CREATE TABLE role_permission (
        role_id INT NOT NULL,
        permission_id INT NOT NULL,
        PRIMARY KEY (role_id, permission_id)
    );

```

</b>

### Sample data

<b>

```sql

    INSERT INTO `schema_mysql`.`roles`(`id`,`role_name`) VALUES (1, 'admin');
    INSERT INTO `schema_mysql`.`roles`(`id`,`role_name`) VALUES (2, 'user');

    INSERT INTO `schema_mysql`.`users` (`username`,`password`,`role_id`) VALUES ('tirmizee','tirmizee', 1);
    INSERT INTO `schema_mysql`.`users` (`username`,`password`,`role_id`) VALUES ('pratya','pratya', 2);

    INSERT INTO `schema_mysql`.`permissions`(`id`,`per_code`,`per_name`) VALUES (1, 'P001', 'Main page');
    INSERT INTO `schema_mysql`.`permissions`(`id`,`per_code`,`per_name`) VALUES (2, 'P002', 'Customer page');
    INSERT INTO `schema_mysql`.`permissions`(`id`,`per_code`,`per_name`) VALUES (3, 'P003', 'Product page');

    
    INSERT INTO `schema_mysql`.`role_permission`(`role_id`,`permission_id`) VALUES (1,1);
    INSERT INTO `schema_mysql`.`role_permission`(`role_id`,`permission_id`) VALUES (1,2);
    INSERT INTO `schema_mysql`.`role_permission`(`role_id`,`permission_id`) VALUES (1,3);
    INSERT INTO `schema_mysql`.`role_permission`(`role_id`,`permission_id`) VALUES (2,1);
    INSERT INTO `schema_mysql`.`role_permission`(`role_id`,`permission_id`) VALUES (2,2);

```

</b>
