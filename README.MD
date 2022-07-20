# JSON Server [![Node.js](https://github.com/typicode/json-server/actions/workflows/node.js.yml/badge.svg?branch=master)](https://www.npmjs.com/package/json-server)


Create `Package.json`

```sh

$ npm init -y

```

Install JSON server by using [npm](https://npmjs.com) package

```sh

$ npm install json-server

```

Install JSON server by using [yarn](https://yarnpkg.com) package

```sh

$ yarn add json-server

```

Config for JSON Server

* open `package.json`

* find scripts 

* add this words

```sh

"serve": "json-server --watch ./data/db.json{path} --port 4000

```
Option :
* `path` - means the location of json file
* `port` - means change working port number 

Run [JSON](https://github.com/typicode/json-server/actions/workflows/node.js.yml/badge.svg?branch=master) Server

[npm](https://npmjs.com) Package - 

```sh

$ npm run serve

```

[Yarn](https://yarnpkg.com) Package - 

```sh

$ yarn serve 

```

**Get Posts**

    localhost:3000/posts

Option - 

* `comments`
* `albums`
* `photos`
* `todos`
* `users`

**Filter** 

    localhost:3000/posts?id=10&userId=10

**Sort**

    localhost:3000/posts?userId=10&_sort=id&_order=desc|asc

Option - 

* `_sort `    - Sorting
* `_order`    - Ordering
* `desc  `    - Descendant
* `asc   `    - Ascendant

**Pagination**

    localhost:3000/posts?_page=1&_limit=10

Option - 

* `_page`     - number of pages
* `_limit`    - number of data

### Search 

    localhost:3000/posts?q=word

Option - 

* `word` - type what you want from data

### Operators

    localhost:3000/posts?id_gte=10&id_lte=15

    localhost:3000/posts?id_ne=1  
    
**Find**

    localhost:3000/posts?id_like=^f  

Option - 
    
* Return start letter with f


### Relationship

    localhost:3000/users?_embed=posts 

    localhost:3000/posts?_expand=user

    localhost:3000/posts?id=1&_expand=user

### Custom Routes

Create `routes.json` and write these code - 

```json

{

    "api/v1/*": "/$1",

    "/posts/:number": "/posts?userid=:number"

}

```

change `package.json` to

```json

"serve": "json-server --watch ./data/db.json --port 4000 --routes ./data/routes.json"

```

and restart the server again

### Generate Custom JSON File by using JavaScript

Create `product.js` and write this codes - 

```js

module.exports = () =>{

    const data = {

        products: [],

    }
    for(let i = 0; i < 100; i++){

        data.products.push({

            id: i,
            title: `products${i}`
        })
    }

    return data
        
}

```
and then change in `package.json`

```json

"serve": "json-server --watch ./data/product.js --port 4000 --routes data/routes.json"

```

and then `restart` [JSON](https://www.npmjs.com/package/json-server) Server again


### Author

**Zaw Linn**

*[GitHub](https://github.com/zawlinn-dev)
*[Facebook](https://facebook.com/zawlinn-profile)
