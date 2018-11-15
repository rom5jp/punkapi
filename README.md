# PUNK API

## Made with:
- ruby 2.4.1p111 (2017-03-22 revision 58053) [x86_64-linux]
- rbenv 1.1.1-6-g2d7cefe
- Rails 5.1.4

## ER diagram
https://imgur.com/a/FPZ3H

## Tests
- FactoryBot instead of fixtures;
- Unit tests;
- Integration tests (request specs);
- I chose to work with requests specs instead of controllers specs due to the recommendation of the creators of Rails and RSpec, since it is a more comprehensive type of test, avoiding unnecessary granularization;
- I'm randomizing the tests order so that can be more robust. You can disable this feature by commenting the line `config.order = :random` at spec_helper.rb;
- I'm using the gem 'spring-commands-rspec' in order to increase the loading speed of the specs;

### How to run the tests
`bundle exec spring rspec`
Somehting like that should be displayed after running this command:

Finished in 2.28 seconds (files took 0.26843 seconds to load)
129 examples, 0 failures

Randomized with seed 49082

## How to run locally:
- Clone this repository
- `bundle install`
- `bundle exec rake db:create`
- `bundle exec rake db:migrate`
- Setup vars at .env file
- I recommend adding the following configuration to your hosts file (/etc/hosts in Linux) `0.0.0.0 punkapi.com`
- `rails s`
- `redis-server`

## Database
- I used PostgreSQL. Remember to edit the database params at .env file.
- You can execute the seeds if you want (seeds.rb)

## How to send requests to the API
- Base URL: http://punkapi.com:3000/v2
- For security reasons, you must send the Accept header with the following value: application/fractal.punk.v2

## Redis
- Don't forget to start the Redis server: opena another terminal window and run `redis-server`

## Etc
- API is versioned
- CORS is enabled
- Rate Limiting and Throttling configured