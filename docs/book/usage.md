# Usage

zend-debug exposes the static method `Zend\Debug\Debug::dump()`, which prints or
returns information about an expression. This simple technique of debugging is
common because it is easy to use in an ad hoc fashion and requires no
initialization, special tools, or debugging environment.

## Example

```php
Zend\Debug\Debug::dump($var, $label = null, $echo = true);
```

The `$var` argument specifies the expression or variable about which the
`Zend\Debug\Debug::dump()` method outputs information.

The `$label` argument is a string to be prepended to the output of
`Zend\Debug\Debug::dump()`. It may be useful, for example, to use labels if you
are dumping information about multiple variables on a given screen.

The boolean `$echo` argument specifies whether the output of
`Zend\Debug\Debug::dump()` is echoed or not. If `TRUE`, the output is echoed.
Regardless of the value of the `$echo` argument, the return value of this method
contains the output.

It may be helpful to understand that ``Zend\Debug\Debug::dump()`` wraps the PHP
function [`var_dump()`](http://php.net/var_dump). If the output stream is
detected as a web presentation, the output of `var_dump()` is escaped using
[`htmlspecialchars()`](http://php.net/htmlspecialchars) and wrapped with HTML
`<pre>` tags.


> ### Debugging with Zend\Log
>
> ``Zend\Debug\Debug::dump()`` is best for ad hoc debugging during software
> development. You can add code to dump a variable and then remove the code very
> quickly.
>
> Also consider the [zend-log component](http://docs.zendframework.com/zend-log/)
> when writing more permanent debugging code. For example, you can use the
> `DEBUG` log level and the
> [stream log writer](http://docs.zendframework.com/zend-log/writers/#writing-to-streams)
> to output the string returned by `Zend\Debug\Debug::dump()`.
