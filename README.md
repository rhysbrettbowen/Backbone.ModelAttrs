# Backbone.ModelAttrs

a simple function that takes a backbone model and returns an object with each of the attributes as a function that will return their value when no arguments passed or set the value when passed an argument. You can chain setting arguments and write code like this:

```javascript
var mod = new Backbone.Model({
	firstName: 'Fred',
	secondName: 'Smith'
});

var names = toAttrs(mod);

names
	.firstName('Bob')
	.secondName('Goldsberg');

names.firstName(); // Bob
```

It returns an object but you can put the functions on the original model by extending it:

```javascript
_.extend(mod, toAttrs(mod));

mod.lastName(); // Goldsberg
```
