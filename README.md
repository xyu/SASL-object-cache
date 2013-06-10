SASL-object-cache
=================

A fork of Memcached Object Cache WordPress plugin,
[Memcached](http://wordpress.org/plugins/memcached/) and
[PHPMemcacheSASL](https://github.com/aarondfrancis/PHPMemcacheSASL) to support
connections to SASL secured memcached clusters.

Install
-------

To install copy both `object-cache.php` and `MemcacheSASL.php` files to the
`wp-content` directory. Also edit `wp-config.php` and add a global configs var
named `$sasl_memcached_config` in the format below:

    $sasl_memcached_config = array(
        'default' => array(
            array(
                'host' => '127.0.0.1',
                'port' => '11211',
                'user' => 'my_username',
                'pass' => 'my_password',
            ),
        ),
    );

In the above example there is only one bucket configured named default which
connects to a memcached server on localhost and the default port using
'my_username' / 'my_password' as auth.

TODO
----

  * MemcacheSASL only supports connection to a single server so only the last
    server in any bucket is used.
  * MemcacheSASL does not support setCompressThreshold() so we don't compress
    anything right now.

