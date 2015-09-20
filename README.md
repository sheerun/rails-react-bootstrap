# Rails-React Bootstrap

Handcrafted bootstrap for Rails & React development.

## Requirements

1. Ruby >= 2.2.3 (needed for newest rails build)
2. Node.js (for assets compilation)

## Decisions

Every feature in this repository is described below. Alternatives are evalutated.

### Rails 5 as default framework

- In my biased opinion Node.js is less reliable for web applications than Rails
- Rails still has active community and maintenance team
- Rails 5 incorporates [Rails API](https://github.com/rails-api/rails-api) that is better suited for SPA applications.
- In my experience developing web apps in light frameworks like pure Rack, Sinatra, Padrino are productive in very short run only. After a short time, you end up re-inventing the wheel.
- EventMachie-based frameworks like Cramp experience a lot of concurrency issues

Downsides:

- We don't need all features of Rails for good SPA application
- Rails & ActiveRecord are considered quite heavy and monolithic solutions

Becuse of those, I might consider [Lotus Framework](http://lotusrb.org/) after it gets stable release.

### PostgreSQL as default database:

* After using MySQL for few years, I experienced a [lot of quirs](http://grimoire.ca/mysql/choose-something-else).
* PostgreSQL is [well-supported by Rails](http://blog.remarkablelabs.com/2012/12/a-love-affair-with-postgresql-rails-4-countdown-to-2013), most noticeably hstore.
* Heroku's preferred db is postgresql (there are mysql addons though).
* SQLite is easy for set-up but using it on development and postgresql on production can lead to production-only bug.
* We can use simple [queue_classic](https://github.com/QueueClassic/queue_classic) worker queue

Downsides:

* Currently there is no good, and free postgresql client for Mac. The ones I am aware of are pgAdmin, Navicat and PG Commander, and pgXplorer.

## License

As Rails, this project is [MIT-licensed](http://opensource.org/licenses/mit-license.php).
