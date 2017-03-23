# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    Inside the router, a developer defines a specific route and the type of request that will be made.  The ember route describes what action will result in a request.  In other words, the ember route defines what will happen with an action and the router defines the url path for the request.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember generate route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{#link-to "boston" campus boston}}Link {{/link-to}}
    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    The first route has a nested path.  Also, in the frist route example, the 'product' route is dependent on the 'products' routes being used.  In other words, you cannot access 'product' without using the 'products' path.  In the second example, on the other hand, acts independently and does not depend on the 'products' route.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    You would have to define a method in the route (not router) where you could indicate how to obtain the value.  This method would need to find the id from the model and the action must refer to the id.
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    You refer to the path, the model and the action you define in the route.
    ```
