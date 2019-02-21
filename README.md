### lowdb
---
https://github.com/typicode/lowdb

```js
db.get('posts')
  .push({ id: 1, title: 'lowdb is awesome'})
  .write()
  
const low = require('lowdb')
const fileSync = require('lowdb/adapters/FileSync')

const adapter = new FileSync('db.json')
const db = low(adapter)

db.defaults({ posts: [], user: {}, count: 0 })
  .write()
  
db.get('posts')
  .push({ id: 1, title: 'lowdb is awesome'})
  .write()
  
db.set('user.name', 'typicode')
  .write()
  
db.update('count', n => n + 1)
  .write()
  
db.get('posts')
  .find({ id: 1 })
  .value()
  
var adapter = new LocalStorage('db')  
var db = low(adapter)
  
db.set('user.name', 'typicode')
  .write()
  
db.set('user.name', 'typicode')  
  .value()
  
db.write()

db._.mixin({
  second: function(array) {
    return array[1]
  }
})

db.get('posts')
  .second()
  .value()

db.getState()

const newState = {}
db.setState(newState)

db.write()
console.log('State has been saved')

db.write()
  .then(() => console.log('State has been saved'))

db.read()
console.log('State has been updated')

db.read()
  .then(() => console.log('State has been updated'))

const adapter = new FileSync('array.yaml', {
  defaultValue: [],
  serialize: (array) => toYamlString(array),
  deserialize: (string) => fromYamlString(string)
})

const adapter = new FileSync('db.json')

db.read()
  .then(() => console.log('Content of my_project/db.json is loaded'))

db.has('posts')
  .value()
  
db.set('posts', [])
  .write()
  
db.get('posts')
  .filter({published: true})
  .sortBy('Views')
  .take(5)
  .value()
  
db.get('posts')
  .map('title')
  .value()
  
db.get('posts')
  .size()
  .value()
  
db.get('posts[0].title')
  .value()
  
db.get('posts')
  .find({ title: 'low!'})
  .assign({ title: 'hi!'})
  .write()
  
db.get('posts')
  .remote({ title: 'low!' })
  .write()

db.unset('user.name')
  .write()

db.get('posts')
  .cloneDeep()
  .value()

const shortid = require('shortid')

const postId = db
  .get('posts')
  .push({ id: shortid.generate(), title: 'low!' })
  .write()
  .id
  
const post = db
  .get('posts')
  .find({ id: postId })
  .value()

const lodashId = require('loadash-id')
const FileSync = require('lowdb/adapters/FileSync')

const adapter = new FileSync('db.json')
const db = low(adapter)

db._.mixin(lodashId)

const collectin = db
  .defaults({ posts: [] })
  .get('posts')

const newPost = collection
  .insert({ title: 'low!' })
  .write(0
  
const post = collection
  .getById(newPost.id)
  .value()
  
class MyStorage {
  constructor() {
  }
  
  read() {
  }
  
  write(data){
  }
}  
const adapter = new MyStorage(args)
const db = low()

const adapter = new FileSync('db.json', {
  serialize: (data) => encrypt(JSON.stringify(data)),
  deserialze: (data) => JSON.parse(decrypt(data))
})
```

```sh
npm install lowdb
yarn add lowdb
```

```
{
  "posts": [
    { "id": 1, "title": "lowdb is awesome"}
  ],
  "user": {
    "name": "typicode"
  },
  "count": 1
}
```
