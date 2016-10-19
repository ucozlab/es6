
### ES6 Features.

# Block scoping variables:

  - ```let``` видны только после обьявления только в текущем блоке.
  - ```let``` Нельзя переобьявлять.
  - в итерации каждый раз новая ```let```;
  - ```const``` Нельзя переприсваивать, в остальном все тоже самое.

# Arrow functions:

  -  new syntax 
  ```functionName () => {}```
  -  если в одну строчку - то значение возвращается (return)
  -  arrow functions binds to the scope, where they are defined.

# Default parameters

  -  в функцию можно передать значение по умолчанию  Exaple: ```loadProfiles( userNames = [] ){ ... }```
  -  можно использовать Named parameters Example:

```sh
function spread( name, {popular, active, activeClass = 2000}) {
   console.log('name', name);
   console.log('popular', popular);
   console.log('active', active);
   console.log('activeClass', activeClass);
};

spread('hello',{
  popular:true,
  active: 'yes',
})
```

# Rest parameters

```sh
function displayTags(someattribute, ...tags) {
	for (a of tags) {
		console.log('...tags for of loop -', a);
	}
	tags.forEach((i)=>console.log('...tags forEach -', i));

	// arguments.forEach((i)=>console.log('...arguments forEach -', i)); // error т.к. коллекция

}

displayTags(5,6,7,8,9,'окно',true);
```

  -  ...tags - это настоящий массив(не коллекция).
  -  ...tags должен быть последним аргументом функции!
  -  можно передавать ...rest в функцию ( не в обьявлении функции а в ее вызове) Exaple:
```sh
var arr = [5,6,7,8,9,'окно',true];
displayTags(...arr); // ...arr разбивается на аргументы, т.е. передается НЕ массивом
```

# Template literals

  -  новый синтаксис для выражений 
  ``` `строка текста ${выражение} строка текста` ```
  -  перенос строки просто ентером
  -  возможность писать для строк функции, и получать в массиве строки и параметры. Example:
  ```sh
tag = (strings, ...values) => {
    console.log(strings);
    console.log(values);
}
var message = tag`Now is ${ new Date().getHours()} another text`;
console.log(message);
```
  
