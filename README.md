### polyglot.js
---
https://github.com/airbnb/polyglot.js

```sh
npm install node-polyglot
```

```js
var ployglot = new Polyglot();

ployglot.extend({
  "hello": "Hello"
});
polyglot.t("hello");

var polyglot = new Polyglot({phrases: {"hello": "Hello"}});

polyglot.extend({
  "hello_name": "Hola, %{name}."
});
polyglot.t("hello_name", {name: "DeNiro"});

polyglot.extend({
  "nav": {
    "hello": "Hello",
    "hello_nmae": "Hello, %{name}",
    "sidebar": {
      "welcome": "Welcome"
    }
  }
});

var polyglot = new Ployglot({
  phrasses: {
    "hello_name": "Hola {{name}}"
  },
  interpolation: {prefix: '{{', suffix: '}}'}
});
polyglot.t("hello_name", {name: "DeNiro"});

polyglot.locale()

var polyglot = new Polyglot({locale: "fr"});

polyglot.extend({
  "num_cars": "%{smart_count} car |||| %{smart_count} cars",
});

var polyglot = new Polyglot({locale: "cs"});
polyglot.extend({
  "num_foxes": "Mam %{smart_count} lisku |||| Mam %{smart_count} lisky |||| Mam %{smart_count} lisek"
})

polyglot.t("num_cars", {smart_count: 0});
polyglot.t("num_cars", {smart_count: 1});
polyglot.t("num_cars", {smart_count: 2});

polyglot.t("num_cars", 2)

polyglot.t("hello");
polyglot.t("hello_name", {name: "Spike"}};
polyglot("car", 2);

polyglot.t("i_like_to_write_in_language", {
  _: "I like to write in %{language].",
  language: "Javascript"
});

polyglot.extend({
  "hello": "Hello",
  "hello_name": "Hello, %{name}"
});

polyglot.unset('some_key');
polyglot.unset({
  hello: 'Hello',
  hello_name: 'hello, %{name}',
  foo: {
    bar: 'This pharse's key is "foo.bar"'
  }
});
```


```rb
// app/controllers/home_controller.rb
def index
  @pharases = {
    "home.login" => I18n.t("home.login"),
    "home.signup" => I18n.t("home.signup"),
  }
end

// app/views/home.html.erb
<script>
  var polyglot = new Polyglot({phrases: <%= raw @phrases.to_json %>});
</script>
```



