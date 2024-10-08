---
title: HTMX Fundamentals
theme: dracula
revealOptions:
  transition: 'slide'
---

## HTMX Fundamentals

Note: Hello everyone! This small brownbag will just go over the fundamentals of HTMX but stay until the end for a small announcement.

---

> HTMX is a library that allows you to access modern browser features directly from HTML, rather than using javascript code.

- **From their website**

---

### Features

<ul>
    <li class="fragment">Use the full suite of request methods: <code>post</code>, <code>get</code>, <code>put</code>, <code>delete</code>, <code>patch</code></li>
    <li class="fragment">Any element can issue requests, not just <code>a</code> and <code>form</code></li>
    <li class="fragment">Interact with more than <code>click</code>, you can interact using <code>hover</code>, <code>blur</code> and others</li>
    <li class="fragment">Target other elements besides the entire window</li>
    <li class="fragment">Defer state management to the backend, through HATEOAS!</li>
</ul>

---

### Wtf is HATEOAS?

A small detour

---

### It's simple

<p class="fragment">Hypermedia As The Engine Of Application State</p>

---

Easy, right? 😅

---

All state is encoded in hypermedia returned by the server.

---

### What does that even mean?

Not logged in

```html[1-5]
<ul>
    <li><a href="/login">Login</a></li>
    <li><a href="/register">Register</a></li>
</ul>
```

Logged in

```html[1-7]
<div>
    <h1>Welcome, John Doe</h1>
</div>
<ul>
    <li><a href="/profile">Profile</a></li>
    <li><a href="/logout">Logout</a></li>
</ul>
```
---

### So why use it?

<ul>
    <li class="fragment">Only show what the user can do</li>
    <li class="fragment">Server only responds with what it knows, not what the client needs to know</li>
    <li class="fragment">Intuitive, discoverable web applications</li>
</ul>

<p class="fragment">HATEOAS is for humans</p>

Note: Mention Roy Fielding's excellent doctoral paper, coining REST

---

### Interesting, but why use HTMX?

---

#### It's very small (around 14kb min.gz)
<ul class="fragment">
    <li>Production-ready</li>
    <li>Plays well with other libraries, including React</li>
    <li>Excelent performance</li>
</ul>

---

#### Simplifies state management
<ul class="fragment">
    <li> No need to manage state in the frontend</li>
    <li> Keep state in the backend, through cookies, headers, or query parameters</li>
</ul>

---

#### Decreases complexity
<ul class="fragment">
   <li>Less code in the frontend == less complexity and code to maintain</li>
</ul>

Note:  One company switched their complex React-based solution for a massive 67% codebase reduction, no loss in functionality https://htmx.org/essays/a-real-world-react-to-htmx-port/

---

#### More languages!
<ul class="fragment">
    <li>HTMX is not tied to a specific language</li>
    <li>Use your favorite backend language to generate HTML</li>
    <li>Stellar support for JS, Typescript, Go.</li>
</ul>

---

#### Use the full power of the browser

<ul class="fragment">
    <li>Caching</li>
    <li>Compression</li>
    <li>Prefetching</li>
</ul>
	
Note: Performant, very similar to a hydrated React page

---


### Sounds good, any downsides?


---

#### Limited interactivity

<p class="fragment">HTMX is not a replacement for React</p>
<ul>
    <li class="fragment">Yes, there are some cases where React is the better choice</li>
    <li class="fragment">However, that is not the majority of the cases. We're talking something like Google Sheets or PWA websites.</li>
    <li class="fragment">HTMX is a great tool for the majority of web applications</li>
</ul>

---

#### Too simple

<ul>
    <li class="fragment">HTMX shines in smaller projects</li>
    <li class="fragment">It's not a silver bullet, but it's a great tool to have in your toolbox</li>
    <li class="fragment">But it can be used in larger projects, see <a href="https://htmx.org/essays/a-real-world-react-to-htmx-port/">https://htmx.org/essays/a-real-world-react-to-htmx-port/</a></li>
</ul>


---

#### Separation of concerns

<ul>
    <li class="fragment">HTMX can make it harder to separate concerns</li>
    <li class="fragment">On the other hand, we already do this on the regular (tailwindui, jsx, react server components)</li>
    <li class="fragment">We gain Locality of Behavior</li>
        <ul class="fragment">
            <li><backquote>The behaviour of a unit of code should be as obvious as possible by looking only at that unit of code</backquote></li>
        </ul>

---

#### JSON API/GraphQL

Hypermedia APIs are not as common as JSON APIs, or in our case GraphQL. So consumers of your API will need to be aware of this.

<ul>
    <li class="fragment">Instead, think of 2 APIs</li>
    <li class="fragment">
        <ul>
            <li>Application Level - generic JSON Data API</li>
            <li>Network Architecture Level - Hypermedia API</li>
        </ul>
    </li>
</ul>

---

#### A different mindset

You will need to think differently about how you structure your application.

<ul>
    <li class="fragment">It's a more full-stack or backend-first approach</li>
    <li class="fragment">State management will be very different</li>
</ul>

---

### Sources 

- https://htmx.org/essays/ HTMX  Essays by Carson Gross
- https://htmx.org/essays/hypermedia-friendly-scripting
- https://hypermedia.systems/ Hypermedia Systems (Carson Gross, Adam Stepinski, Deniz Akşimşek, 2023)
- https://ics.uci.edu/~fielding/pubs/dissertation/top.htm  Architectural Styles and  
the Design of Network-based Software Architectures, (Roy Fielding, 2000)

---

## Q&A

---

# THANK YOU
