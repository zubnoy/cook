Cook
====
Cook is a tool for building projects in D language.

In contrast to other build automation programs, Cook by default requires no configuration file - it automatically collects information about source code from D source files in project directory.

How it works?
-------------
To determine which module needs recompiling, Cook traces dependencies between all of them. To do this properly, it performs lexical analyzis, which is a relatively expensive procedure. But, actually, it's not neccessary to always do full scanning, except the very first time. Cook writes all metadata into cache file, and then uses it, invoking lexer only for modules that has changed, and those which depend on them. A process is a kind of chain reaction - if a module needs recompiling, everything that rely on it also needs recompiling, and so on. This approach is especially useful in compilcated template-based environments.
System requirements

Cook is written in D2/Phobos and supports Windows and Linux. By default it works with Digital Mars D compiler (DMD), but you can use other compilers as well by writing proper configuration file. See documentation for details.

Cook users
----------
* [dlib](http://github.com/gecko0307/dlib "dlib") - D language utility library
* [Atrium](http://github.com/gecko0307/atrium "atrium") - in-development 3D game written in D 