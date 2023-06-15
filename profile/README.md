
# The ecosystem around Signal abstraction.

We can see the different versions of implementations of one algoritm.
- @preactjs/signals-react
- @angular/signals
- MobX, Vue, SolidJS
And each time it's different implementation. If you see to source code of each one, everythere implementation will be different.

Programmer friends, I urge you. Let's write the minimum and most productive code for this algorithm and offer to integrate it into all these libraries. This is how we can maximize the growth of reactive library syntax improvement, as well as the performance increase for all of these frameworks.

Minimal algoritm implementation currenty located in the [re-js/reactive-box](https://github.com/re-js/reactive-box). Repository also contains the tests for algoritm checking.

I will ask attention especially from masters of olympiados, and amazing kind guys who have keen, hudge, and clever interest in the complex algorithmic task!

## Signal abstraction

**Signal** - It's a _container_ with value. Each time when value changed, container notify subscribers. It's a basic reactive element can be used for store any values that can be compared by equlity via comparer function. Using the different comparer function you can get "shallow" or "deep" equality.

```javascript
const [get, set] = signal(0)
```

The second element is the reaction. The primary reason of popularity Signal abstraction is the convinient syntax for collect reactive dependencies. It happens transparently.

```javascript
effect(
  () => console.log(get())
)
```

The third element is the computed.

```javascript
const [getC] = computed(() => get() + 5)
```

Necessary to implement these tree primary element. And two additional "untracked", and "batch", but late.

[Play with minimal implementation on Codesandbox](https://codesandbox.io/s/unruffled-cerf-ddtt6s?file=/src/signals.js) https://codesandbox.io/s/unruffled-cerf-ddtt6s?file=/src/signals.js

Enjoy you state!

