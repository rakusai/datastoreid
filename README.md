# Datastoreid

Datastoreid is an ODM (Object-Document-Mapper) framework for Google Datastore in Ruby.

Install
-------
```sh
gem build datastoreid.gem
gem install datastoreid-<version>.gem
```
or
```ruby
gem 'datastoreid', '~> 0.4.0', git: 'https://github.com/fabiotomio/datastoreid'
```

Configure
---------
```sh
export DATASTORE_EMULATOR_HOST_PATH=datastore:8181/datastore
export DATASTORE_EMULATOR_HOST=datastore:8181
export DATASTORE_DATASET=<project-id>
export DATASTORE_PROJECT_ID=<project-id>
```

Use
-------
```ruby
# Define product model product.rb
class Product
  include Datastoreid::Entity # inject entity behaviour
  include Datastoreid::Timestamps # add created and updated properties

  kind 'Product' # Datastore Kind

  property :barcode 
  property :name
  property :price

  validates :barcode, :name, :price, presence: true
end
```
