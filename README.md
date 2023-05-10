# yaff - Yet Another Front-end Framework
View, Model, Collection, Events and routing - just all you need to build modern app

**packages**:  

## [yaff-events](https://github.com/taburetkin/yaff-events) (✅published)
Events api for event-driven mechanics.  
stand alone
### Example
```js
import { Events } from 'yaff-events';

class MyClass {}
Object.assign(MyClass.prototype, Events);


const instance = new MyClass();
const another = new MyClass();

// registering event callback
instance.on('event', () => { console.log('event!') });
// triggering event
instance.trigger('event');
// console:
// event!

another.listenTo(instance, 'event', () => { console.log('once more!') })
instance.trigger('event');
// console:
// event!
// once more
```

## [yaff-routing](https://github.com/taburetkin/yaff-routing) (✅published)
Routing api for route-based applications.  
stand alone
### Example
```js
import { routing } from 'yaff-routing';

//define middleware for root page http://localhost
routing.get('', () => {
  console.log('this is main page');
});

//define middleware for articles page http://localhost/articles
routing.get('articles', () => {
  console.log('this is articles page');
});
```

## [yaff-core](https://github.com/taburetkin/yaff-core) (in development)   
Common things for other yaff packages.  

## [yaff-model](https://github.com/taburetkin/yaff-model) (in development)
Data manipulation framework: Model, Collection, etc.  
peer dependecies on: `yaff-core`, `yaff-events`
### Example
```js

import { Model } from 'yaff-model';

const model = new Model({ name: 'Peter', age: 18 });

model.set('age', 19);
model.get('age'); // 19

```


## [yaff-view](https://github.com/taburetkin/yaff-view) (in development)
DOM manipulation framework: View  
peer dependecies on: `yaff-core`, `yaff-events`
### Example
```js

import { View, attachView } from 'yaff-view';

const view = new View({
  template: () => '<h1>hello world!</h1>',
});
attachView(view, document.body);



```