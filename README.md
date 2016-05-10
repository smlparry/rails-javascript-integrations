<<<<<<< 8a6e99803afc4fd4e84355e6158f83b14fabafbd
# Rails JavaScript Integration Strategies

## Why this?

Componentized views make UI development orders of magnitude simpler. Unfortunately, scaling UI development and integrating a modern JavaScript workflow into a new or existing Rails app can be tricky.

## What is this?

This project builds a simple todo list component with 4 different JavaScript integration strategies:

- __[scoped-jquery](https://github.com/chrisvfritz/rails-javascript-integrations/tree/scoped-jquery)__: I wouldn't actually recommend this for anyone. But, if your team is currently using jQuery and adopting a new framework is a tough sell right now, here's a relatively simple pattern that may help.
- __[vue-simple](https://github.com/chrisvfritz/rails-javascript-integrations/tree/vue-simple)__: A fantastic strategy for existing projects, as Vue plays well with jQuery and other DOM-manipulating libraries. This integration strategy also requires less than 1 minute of setup! As for learning curve, becoming very productive in Vue takes less than a day.
- __[vue-browserify](https://github.com/chrisvfritz/rails-javascript-integrations/tree/vue-browserify)__: Recommended strategy for most new projects. It takes about a half hour to set up, offers a UMD module system, very nice workflow with hot module reloading, and best of all - the configuration is simple enough that it's actually possible for mere mortals to understand everything that's happening!
- __[vue-webpack](https://github.com/chrisvfritz/rails-javascript-integrations/tree/vue-webpack)__: Recommended for people who want to be on the cutting edge and are willing to dive into the guts of build tools. It offers the best possible workflow and tooling possible _for any framework_ at the time of writing.

## How do I use this?

There are two recommended ways of browsing this project. The first is to read the diffs between branches in order of rising complexity. The current branch (`master`) is just a newly generated Rails app.

1. __[master..scoped-jquery](https://github.com/chrisvfritz/rails-javascript-integrations/compare/master...scoped-jquery)__: Adds the todo model and API, with a single JavaScript file.
2. __[scoped-jquery..vue-simple](https://github.com/chrisvfritz/rails-javascript-integrations/compare/scoped-jquery...vue-simple)__: Converts the scoped jQuery to a much simpler Vue component.
3. __[vue-simple..vue-browserify](https://github.com/chrisvfritz/rails-javascript-integrations/compare/vue-simple...vue-browserify)__: Moves all JavaScript to a new `frontend` folder managed by Browserify. Components are also organized into more advanced components in `.vue` files.
4. __[vue-browserify..vue-webpack](https://github.com/chrisvfritz/rails-javascript-integrations/compare/vue-browserify...vue-webpack)__: Bypasses sprockets and all view-related Rails features, now managing the entire UI in the `frontend` folder through Webpack.

If there's a specific setup you're interested in and you want to see all work done from the point of a newly generated Rails app, just diff with `master`:

- __[master..scoped-jquery](https://github.com/chrisvfritz/rails-javascript-integrations/compare/master...scoped-jquery)__
- __[master..vue-simple](https://github.com/chrisvfritz/rails-javascript-integrations/compare/master...vue-simple)__
- __[master..vue-browserify](https://github.com/chrisvfritz/rails-javascript-integrations/compare/master...vue-browserify)__
- __[master..vue-webpack](https://github.com/chrisvfritz/rails-javascript-integrations/compare/master...vue-webpack)__

## FAQ

### What about examples using [React instead of Vue](https://vuejs.org/guide/comparison.html#React)?

I used React pretty heavily for over a year. I still do sometimes. Many companies and individual developers I work with still think of me as "the React guy". I'm grateful for React. It was instrumental in helping me understand the value of component-based UI development.

Please consider this when I say that almost everything React does, Vue does better. It's both simpler _and_ more powerful. It makes my applications even easier to reason about. It includes many essential features missing in React, such as a built-in transition system - yet maintains a smaller build size. It simply makes me happier and more productive. 

Try it - it might do the same for you. You can seriously learn the essentials and be building non-trivial applications in less than a day.

### What about examples using Angular 2? They use components, right?

Angular 2 isn't out yet - but even despite that, the way it's engineered means that even the simplest possible integration is more complex than all but the most advanced one currently included here. And you don't get anything extra in return for that complexity. In fact, you'd have a _worse_ development experience and a much larger build right from the start. So I don't see the point.

Also as an aside, they have a whopping 1,461 open issues as of writing!! Over the last few months, that number has even been growing, not shrinking. At this rate, I'm not sure they'll _ever_ release. :confused:

If you're just a TypeScript fan though, there's good news! You can use it with Vue. [It's on DefinitelyTyped.](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/vue)

## Contributing

If you notice a mistake, room for improvement, or have questions, issues and pull requests are very welcome. :smile:
=======
# Pure Sprockets with Vue

This version uses the Rails asset pipeline, plain ES5 JavaScript, the jQuery that ships with Rails, and Vue.js to make componentization much simpler.

## Setup

Less than 1 minute using [vuejs-templates/simple](https://github.com/vuejs-templates/simple) as a reference.

## Usage

Just launch Rails normally:

```
rails server
```

## Pros

- __(Almost) zero setup__: Beyond our one JS file, we also add a dependency in our application layout and add a line to `application.js` (there's also [a `vuejs-rails` gem](https://github.com/adambutler/vuejs-rails) for simple asset pipeline integration)
- __Plain ES5__: no Babel or CoffeeScript required, though CoffeeScript support _also_ comes out of the box
- __Progressive__: The parts of the app that have to be smart are, but everything else is just regular HTML
- __Really simple scoping__: No extra classes, just custom elements
- __Plays well with jQuery__: If you have existing UI controlled by jQuery, Vue won't freak out and break like React does
- __jQuery UJS__: Rails' builtin jQuery UJS automatically sends the authenticity token in the header of jQuery's web requests
- __Less thinking__: Using a simple component framework, there's a clear place for everything and a clear strategy for tackling any problem
- __Minimized boilerplate__: The template reads easily and clearly describes what the component does, even for people who don't understand JavaScript

## Cons

- __Still kinda ugly HTML__: No HTML syntax highlighting and we have to use a lot of backslashes to escape the multiline string
- __Requires a little learning__: A few hours with [the _excellent_ Vue docs](http://vuejs.org/guide/) is recommended to be optimally productive
>>>>>>> added readme
