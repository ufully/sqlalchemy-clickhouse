sqlalchemy-clickhouse
=====================

ClickHouse dialect for SQLAlchemy.

Installation
------------

The package is installable through PIP::

   pip install sqlalchemy-clickhouse

Usage
-----
add local timezone support
default is 0

   os.environ.setdefault('CLICKHOUSE_USE_LOCAL_TIMEZONE', '0')

   os.environ.setdefault('CLICKHOUSE_USE_LOCAL_TIMEZONE', '1')

--------------------------------------------------

The DSN format is similar to that of regular Postgres::

    >>> import sqlalchemy as sa
    >>> sa.create_engine('clickhouse://username:password@hostname:port/database')
    Engine('clickhouse://username:password@hostname:port/database')

It implements a dialect, so there's no user-facing API.

Testing
-------

The dialect can be registered on runtime if you don't want to install it as::

    from sqlalchemy.dialects import registry
    registry.register("clickhouse", "base", "dialect")
