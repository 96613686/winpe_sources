# FuncUnEntityUri::Invoke

- ea: `0x55620`
- end: `0x55639`
- name: `FuncUnEntityUri::Invoke`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x5562d`: `unparsed-entity-uri`

## pseudocode

```c

```

## disassembly

```asm
0x55620  ldstr    aXsltUnsuppfunc// "Xslt_UnsuppFunction"
0x55625  ldc.i4.1
0x55626  newarr   [mscorlib]System.String
0x5562b  dup
0x5562c  ldc.i4.0
0x5562d  ldstr    aUnparsedEntity// "unparsed-entity-uri"
0x55632  stelem.ref
0x55633  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x55638  throw
```
