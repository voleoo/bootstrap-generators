# Bootstrap Generators

[![Build Status](https://travis-ci.org/decioferreira/bootstrap-generators.png?branch=master)](https://travis-ci.org/decioferreira/bootstrap-generators)

Bootstrap-generators provides [Twitter Bootstrap](http://twitter.github.com/bootstrap/) generators for Rails 4 (supported Rails >= 3.1). Bootstrap is a toolkit from Twitter designed to kickstart development of webapps and sites.

## Current Twitter Bootstrap version

The current version of Twitter Bootstrap is 2.3.2.

## Installing Gem

In your Gemfile, add this line:

    gem 'bootstrap-generators', '~> 2.3'

Or you can install from latest build:

    gem 'bootstrap-generators', :git => 'git://github.com/decioferreira/bootstrap-generators.git'

By default Bootstrap Generators requires [SimpleForm 2.0](https://github.com/plataformatec/simple_form). Add the dependency on your Gemfile:

    gem 'simple_form'

If you don't want to use SimpleForm, just pass the `--form_builder=form_builder` option:

    rails generate bootstrap:install --form_builder=form_builder

Run bundle install:

    bundle install

## Generators

Get started:

    rails generate bootstrap:install -f

Once you've done that, any time you generate a controller or scaffold, you'll get [Bootstrap](http://twitter.github.com/bootstrap/) templates.

### Give it a try

    rails generate scaffold post title:string body:text published:boolean

You can easily customize colors, grid system, fonts, and much more by editing `bootstrap-variables.[less|scss]` on your application assets folder.

## Usage

To print the options and usage run the command `rails generate bootstrap:install --help`

    rails generate bootstrap:install [options]

    Options:
          [--layout=LAYOUT]                         # Bootstrap layout templates (hero or fluid)
                                                    # Default: hero
          [--form-builder=FORM_BUILDER]             # Select your form builder (simple_form or form_builder)
                                                    # Default: simple_form
      -e, [--template-engine=TEMPLATE_ENGINE]       # Indicates when to generate template engine
                                                    # Default: erb
      -se, [--stylesheet-engine=STYLESHEET_ENGINE]  # Indicates when to generate stylesheet engine
                                                    # Default: scss

    Runtime options:
      -f, [--force]    # Overwrite files that already exist
      -p, [--pretend]  # Run but do not make any changes
      -q, [--quiet]    # Supress status output
      -s, [--skip]     # Skip files that already exist

    Copy BootstrapGenerators default files

### Options

#### Layouts

There are the two available layouts, based on Bootstrap's quick-start examples:

* [Basic marketing site](http://getbootstrap.com/2.3.2/examples/hero.html) (default)
* [Fluid layout](http://getbootstrap.com/2.3.2/examples/fluid.html)

To select one of these layouts just pass the option `--layout=LAYOUT` to the install generator.

#### Form builders

* SimpleForm

By default Bootstrap Generators requires SimpleForm 2.0. Add the dependency on your Gemfile:

    gem 'simple_form'

And then run:

    rails generate bootstrap:install --form_builder=simple_form

* Default Rails form builder

If you don't want to use SimpleForm, just pass the `--form_builder=form_builder` option:

    rails generate bootstrap:install --form_builder=form_builder

#### Template engines

Supported template engines:

* ERB
* Haml

##### Haml

Add the dependency on your Gemfile:

    gem 'haml-rails'

And then run:

    rails generate bootstrap:install --template-engine=haml

#### Stylesheet engines

Supported stylesheet engines:

* CSS
* SCSS
* LESS

##### SCSS

Make sure you have `sass-rails` dependency on your Gemfile:

    gem 'sass-rails'

And then run:

    rails generate bootstrap:install --stylesheet-engine=scss

Now you can customize the look and feel of Bootstrap.

##### LESS

Add the dependency on your Gemfile:

    gem 'less-rails'

And then run:

    rails generate bootstrap:install --stylesheet-engine=less

Now you can customize the look and feel of Bootstrap.

## Assets

<a name="customize"></a>

### Customize and extend Bootstrap

In Rails 3.0 and above, generators don’t just look in the source root for templates, they also search for templates in other paths. And one of them is lib/templates.

### Javascript

Select all jQuery plugins (`app/assets/javascripts/bootstrap.js`)

    //= require bootstrap

Or quickly add only the necessary javascript (Transitions: required for any animation; Popovers: requires Tooltips)

    //= require bootstrap-transition
    //= require bootstrap-modal
    //= require bootstrap-tooltip
    //= require bootstrap-popover
    //= require bootstrap-alert
    //= require bootstrap-collapse
    //= require bootstrap-tab
    //= require bootstrap-dropdown
    //= require bootstrap-typeahead
    //= require bootstrap-scrollspy
    //= require bootstrap-button
    //= require bootstrap-affix
    //= require bootstrap-carousel


## Customizing Templates

In Rails 3.0 and above, generators don’t just look in the source root for templates, they also search for templates in other paths. And one of them is lib/templates.

Since Bootstrap Generators installs its templates under lib/templates, you can go and customize them.

## Credits

* [Twitter Bootstrap](http://twitter.github.com/bootstrap)
* [Twitter Bootstrap - Sass Conversion](https://github.com/jlong/sass-twitter-bootstrap)
* [SimpleForm](https://github.com/plataformatec/simple_form)

[customize]: #customize
