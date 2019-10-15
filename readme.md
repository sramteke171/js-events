[![General Assembly Logo](https://camo.githubusercontent.com/1a91b05b8f4d44b5bbfb83abac2b0996d8e26c92/687474703a2f2f692e696d6775722e636f6d2f6b6538555354712e706e67)](https://generalassemb.ly/education/web-development-immersive)

# JavaScript Events

So far, the only way we've been able to interact with the applications we've
built so far is through the REPL in the browser. It's too much for us to ask our
users to do the same! So, instead, we want to build applications that respond to
our user's input: a user clicks a button, triggering an action in our
application.

We've learned HTML and CSS, the tools we need to built out the interface; we've
also learned JavaScript, the programming language we can use to build programs;
now, we need to bring the two together and build interfaces (using HTML and CSS)
with functionality our users can leverage (using JavaScript).

The **DOM** not only lets us manipulate the document (or webpage) using
JavaScript, but also gives us the ability to write JavaScript that responds to
interactions within the page. These interactions are communicated as **events**.

We can **listen** for certain kinds of user-driven events, such as clicking a
button, entering data into a form, keypresses and many, many more.

## Prerequisites

- HTML, CSS, and JavaScript
- The DOM & DOM Selectors

## Objectives

By the end of this, developers should be able to:

- Explain event-driven development
- Discover some of the different types of events we can work with in JavaScript
- Define Event Listeners and Event Handlers

## Events

**Discussion Questions:**

- In plain English, what is an event?
- What might an event in the context of a web page be?
- What are some specific examples of common DOM events? (What DOM events did you
  learn in the pre-work?)

> You can find information on events and examples at the
> [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/Events).

"DOM Events are sent to notify code of interesting things that have taken
place." _- MDN_

For the time being, when we talk about "interesting things that have taken
place" we are talking about user interactions with the page. In the context of
JavaScript and building web pages, we are talking about listening for events on
DOM elements and triggering some action in response to those events.

In code, it looks like this:

```js
const button = document.querySelector(".js-button");

button.addEventListener("click", function() {
  alert("You clicked a button!");
});
```

> We'll work through each part of the above snippet in detail as we work through
> the rest of the lesson. In a few minutes, you'll be working with events on
> your own!

## Types of Events

Let's start by answering the question, "What kinds of events can we respond to?"
There are many events that we can listen for and respond to in JavaScript.
Broadly speaking, we can divide these events in to four categories:

### 1. Document / Window Events

- load
- resize
- scroll
- unload

### 2. Mouse Events

- click
- dblclick
- mouseenter
- mouseleave

### 3. Key Events

- keypress
- keydown
- keyup

### 4. Form Events

- submit
- change
- focus

## Event Listeners in JavaScript

When we want to respond to events in JavaScript, we do so in two parts:

1. We set up an event listener with `.addEventListener`
1. We define an event handler, a callback function that get's passed to
   `.addEventListener`

### Step 1: Event Listener

In order to listen for an event, we need to define an **event listener**. Below
you'll find a simple event listener associated with a `'click'` event on a
`button` element.

First we target the button:

<details>
  <summary>If a button element has a class of <code>.js-button</code>, how would we capture this from the DOM?</summary>

```js
const button = document.querySelector(".js-button");
```

</details>

Once we have the element from the DOM, we can tell JS to listen for an event:

```js
// This is the event listener

button.addEventListener("click", handleClickEvent);

// first argument: event, as a string
// second argument: callback function for our event handler
```

That completes step 1 of working with events - we're now listening for a click
event on our button!

### Step 2: Event Handler

For step two, we need to define the function that will be called whenever this
event is emitted. This is just a function, but it has a special name due to how
it's being used: a **callback** function:

```js
function handleClickEvent() {
  console.log("I was clicked!");
}
```

All together, our code looks like this:

```js
const button = document.querySelector(".js-button");

button.addEventListener("click", handleClickEvent);

function handleClickEvent() {
  console.log("I was clicked!");
}
```

You will most often see (and probably use) an anonymous callback function for
your event handler. That looks like this:

```js
const button = document.querySelector(".js-button");

button.addEventListener("click", function() {
  console.log("I was clicked!");
});
```

<details>
  <summary>What is this code doing?</summary>

The code above first gets an element from the DOM. It then attaches an event
listener to that <code>button</code> element with the
<code>addEventListener()</code> method. The <code>addEventListener()</code>
method takes two arguments:

<ol>
  <li>the event we want to listen for, and</li>
  <li>the function that should be called whenever that event is invoked.</li>
</ol>

In the case of the code above, we're saying we want to listen for
<code>click</code> events on our <code>button</code>, and whenever someone does
click on our button, call the <code>handleClickEvent()</code> function.

</details>

## We Do: Practice

> 5 minutes exercise. 5 minutes review.

Go to this
[repository](https://git.generalassemb.ly/dc-wdi-fundamentals/event-listener-practice)
and follow the instructions.

## You Do: Color Scheme Switcher

> 10 min practice / 5 min review

We will build on the Color Scheme Switcher as we work through the following
sections of the lesson.

Visit this
[repository](https://git.generalassemb.ly/dc-wdi-fundamentals/color-scheme-switcher)
and follow along!

## You Do: DOTS: The Game

Visit this
[repository](https://git.generalassemb.ly/dc-wdi-fundamentals/event-listener-demo)
and follow the instructions.

## Additional Resources

- [Build a Drum Kit in Vanilla JS](https://www.youtube.com/watch?v=VuN8qwZoego)
- [Event reference](https://developer.mozilla.org/en-US/docs/Web/Events)
- [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
- [Eloquent JavaScript: Handling Events](http://eloquentjavascript.net/14_event.html)
- [Philip Roberts: What the heck is the event loop anyway?](https://www.youtube.com/watch?v=8aGhZQkoFbQ)

## [License](LICENSE)

1. All content is licensed under a CC­BY­NC­SA 4.0 license.
1. All software code is licensed under GNU GPLv3. For commercial use or
   alternative licensing, please contact legal@ga.co.
