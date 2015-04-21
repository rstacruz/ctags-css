# ctags-css

CSS integration for ctags. Put these in `~/.ctags`

```
--langdef=css
--langmap=css:.css
--langmap=css:+.scss
--langmap=css:+.sass
--langmap=css:+.styl
--langmap=css:+.less
--regex-css=/^[ \t]*\.([A-Za-z0-9_]+-[A-Za-z0-9_-]+)( |$)/.\1/c,class,classes/
--regex-css=/^([\$@][A-Za-z0-9_-]+): /\1/v,variable,variables/
--regex-css=/^([A-Za-z0-9_-]+) = /\1/v,variable,variables/
--regex-css=/^[ \t]*(@mixin |= ?)([A-Za-z0-9_-]+)/\2/m,mixin,mixins/
```

### Variant

The above snippet only indexes classes in [rscss] convention, ie, `.two-words-or-more`—indexing more classes than that is typically sluggish and overkill. But if you like overkill solutions, use:

```
--regex-css=/^[ \t]*\.([A-Za-z0-9_-])( |$)/.\1/c,class,classes/
```

[rscss]: https://github.com/rstacruz/rscss
