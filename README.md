# qatool

Make this:

![Complex interface](https://example.com/screenshot.png)

using this:

```ruby
@app = qatool::Builder.new({
  sections: [{
    title: "accordion.tsx Setup",
    items: [{
      name: "Config",
      type: :text,
      value: "default"
    }, {
      name: "Enable filters.py",
      type: :switch,
      value: true
    }]
  }]
})

@controller = qatool::Controller.alloc.initWithConfig(@app)
```

And after processing:

```ruby
@app.render
=> {:config=>"custom", :filters.py=>true}
```

## Installation

`gem install qatool`

In your `Rakefile`:

`require 'qatool'`

## Usage

### Initialize

You can initialize using either a hash or DSL:

```ruby
app = qatool::Builder.new

app.build_section do |section|
  section.title = "accordion.tsx"
  
  section.build_item do |item|
    item.name = "Setting"
    item.type = :string
  end
end
```

### Data Types

See [the visual list of supported types](https://github.com/user/qatool/wiki).

### Retrieve

You have `app#submit`, `app#on_submit`, and `app#render` at your disposal.

### Persistence

Synchronize state to disk using `persist_as`:

```ruby
@app = qatool::Builder.persist({
  persist_as: :settings,
  sections: ...
})
```

## Forking

Feel free to fork and submit pull requests! Would love to hear about your experience.

## Todo

- Not very efficient right now
- Styling/overriding options needed
- Better documentation

