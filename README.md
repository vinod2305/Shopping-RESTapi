# Shopping API

## Description

- Built a REST Api in Node.js using MVC approch by leveraging Node.js + MongoDB.
- User JWT for Authetication and Authorization.
- A RESTful Api built for serving as a Backend for a Shopping Cart.

## Requirements

For development, you will only need Node.js and a node global package, Yarn, installed in your environement.

### Node
- #### Node installation on Windows

  Just go on [official Node.js website](https://nodejs.org/) and download the installer.
Also, be sure to have `git` available in your PATH, `npm` might need it (You can find git [here](https://git-scm.com/)).

- #### Node installation on Ubuntu

  You can install nodejs and npm easily with apt install, just run the following commands.

      $ sudo apt install nodejs
      $ sudo apt install npm

- #### Other Operating Systems
  You can find more information about the installation on the [official Node.js website](https://nodejs.org/) and the [official NPM website](https://npmjs.org/).

If the installation was successful, you should be able to run the following command.

    $ node --version
    v8.11.3

    $ npm --version
    6.1.0

If you need to update `npm`, you can make it using `npm`! Cool right? After running the following command, just open again the command line and be happy.

    $ npm install npm -g


## Install

    $ git clone https://github.com/vinod2305/Shopping-RESTapi.git
    $ cd Shopping-RESTapi
    $ npm install

## Running the project

    $ npm start


# Shopping Api



## Indices

* [User](#user)

  * [POST - signup](#1-post---signup)
  * [POST - login](#2-post---login)
  * [DELETE - delete user](#3-delete---delete-user)



* [Product](#product)

  * [GET - get all products](#1-get---get-all-products)
  * [GET - get product](#2-get---get-product)
  * [POST - create product](#3-post---create-product)
  * [UPDATE - update product](#4-update---update-product)
  * [DELETE - delete product](#5-delete---delete-product)


* [Order](#order)

  * [GET - get all orders](#1-get---get-all-orders)
  * [GET - get order](#2-get---get-order)
  * [POST - create order](#3-post---create-order)
  * [DELETE - delete order](#4-delete---delete-order)

--------

## User

### 1. POST - signup
***Endpoint:***

```bash
Method: POST
Type: RAW
URL: http://localhost:3000/user/signup
```
***Body:***

```js        
{
    "email":"test1@gmail.com",
    "password": "password"
}
```
##### I. Example Response: POST - signup
```js
{
    "message": "User created"
}
```
***Status Code:*** 201


### 2. POST - login
***Endpoint:***
```bash
Method: POST
Type: RAW
URL: http://localhost:3000/user/login
```
***Body:***
```js        
{
    "email":"test1@gmail.com",
    "password": "password"
}
```
##### I. Example Response: POST - login
```js
{
    "message": "Auth successful",
    "token": {token}
}
```
***Status Code:*** 201



### 3. DELETE - delete user
***Endpoint:***

```bash
Method: DELETE
Type: 
URL: http://localhost:3000/user/60ddabe0d864375a684dc930
```

##### I. Example Response: DELETE - delete user
```js
{
    "message": "User deleted"
}
```

***Status Code:*** 200







## Product

### 1. GET - get all products
***Endpoint:***

```bash
Method: GET
Type: 
URL: http://localhost:3000/products
```
##### I. Example Response: GET - get all products
```js
{
    "count": 1,
    "products": [
        {
            "name": "Test product",
            "price": 100,
            "_id": "60ddb145d864375a684dc933",
            "productImage": "uploads/2021-07-01T12:12:53.719Ztestproduct.jpeg",
            "request": {
                "type": "GET",
                "url": "http://localhost:3000/products/60ddb145d864375a684dc933"
            }
        }
    ]
}
```
***Status Code:*** 200

### 2. GET - get product
***Endpoint:***

```bash
Method: GET
Type: 
URL: http://localhost:3000/products/60ddb145d864375a684dc933
```

##### I. Example Response: GET - get product
```js
{
    "product": {
        "_id": "60ddb145d864375a684dc933",
        "name": "Test product",
        "price": 100,
        "productImage": "uploads/2021-07-01T12:12:53.719Ztestproduct.jpeg"
    },
    "request": {
        "type": "GET",
        "description": "GET ALL PRODUCTS",
        "url": "http://localhost/product"
    }
}
```
***Status Code:*** 200


### 3. POST - create product
***Endpoint:***

```bash
Method: POST
Type: FORMDATA
URL: http://localhost:3000/products
```

***Body:***

| Key | Value | Description |
| --- | ------|-------------|
| name | Test product | Name of the product |
| price | 100 | Price of product |
| productImage |  | File |
***More example Requests/Responses:***
##### I. Example Response: POST - create product
```js
{
    "message": "Created product successfully",
    "createdProduct": {
        "name": "Test product",
        "price": 100,
        "_id": "60de8d65024f812237aec95e",
        "productImage": "uploads/2021-07-02T03:52:05.675Ztestproduct.jpeg",
        "request": {
            "type": "GET",
            "url": "http://localhost:3000/products/60de8d65024f812237aec95e"
        }
    }
}
```
***Status Code:*** 201



### 4. UPDATE - update product
***Endpoint:***

```bash
Method: PATCH
Type: RAW
URL: http://localhost:3000/products/60ddb145d864375a684dc933
```
***Body:***

```js        
[
    {
        "price": "150"
    }
]
```
##### I. Example Response: UPDATE - update product
```js
{
    "message": "Product updated",
    "request": {
        "type": "GET",
        "url": "http://localhost/product/60ddb145d864375a684dc933"
    }
}
```
***Status Code:*** 200



### 5. DELETE - delete product
***Endpoint:***

```bash
Method: DELETE
Type: 
URL: http://localhost:3000/products/60ddb145d864375a684dc933
```

##### I. Example Response: DELETE - delete product
```js
{
    "message": "Product Deleted",
    "request": {
        "type": "POST",
        "url": "http://localhost:3000/products",
        "body": {
            "name": "String",
            "price": "Number"
        }
    }
}
```
***Status Code:*** 200




## Order

### 1. GET - get all orders

***Endpoint:***

```bash
Method: GET
Type: 
URL: http://localhost:3000/orders
```
##### I. Example Response: GET - get all orders
```js
{
    "count": 1,
    "orders": [
        {
            "_id": "60ddb47ad864375a684dc936",
            "product": {
                "_id": "60ddb395d864375a684dc934",
                "name": "Test product"
            },
            "quantity": 20,
            "request": {
                "type": "GET",
                "url": "http://localhost:3000/orders/60ddb47ad864375a684dc936"
            }
        }
    ]
}
```
***Status Code:*** 200




### 2. GET - get order
***Endpoint:***

```bash
Method: GET
Type: 
URL: http://localhost:3000/orders/60ddb47ad864375a684dc936
```
##### I. Example Response: GET - get order
```js
{
    "order": {
        "quantity": 20,
        "_id": "60ddb47ad864375a684dc936",
        "product": {
            "_id": "60ddb395d864375a684dc934",
            "name": "Test product",
            "price": 100,
            "productImage": "uploads/2021-07-01T12:22:45.184Ztestproduct.jpeg",
            "__v": 0
        },
        "__v": 0
    },
    "request": {
        "type": "GET",
        "url": "http://localhost:3000/orders"
    }
}
```
***Status Code:*** 200






### 3. POST - create order

***Endpoint:***

```bash
Method: POST
Type: RAW
URL: http://localhost:3000/orders
```
***Body:***

```js        
{
    "productId": "60ddb395d864375a684dc934",
    "quantity": "20"
}
```
##### I. Example Response: POST - create order
```js
{
    "message": "Order stored",
    "createdOrder": {
        "_id": "60ddb42bd864375a684dc935",
        "product": "60ddb395d864375a684dc934",
        "quantity": 20
    },
    "request": {
        "type": "GET",
        "url": "http://localhost:3000/orders/60ddb42bd864375a684dc935"
    }
}
```
***Status Code:*** 201

### 4. DELETE - delete order
***Endpoint:***

```bash
Method: DELETE
Type: 
URL: http://localhost:3000/orders/60ddb47ad864375a684dc936
```
##### I. Example Response: DELETE - delete order
```js
{
    "message": "Order deleted",
    "request": {
        "type": "POST",
        "url": "http://localhost:3000/orders",
        "body": {
            "productId": "ID",
            "quantity": "Number"
        }
    }
}
```
***Status Code:*** 200









---
[Back to top](#shopping-api)
