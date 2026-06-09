# System.Xml.Xsl.Runtime.XmlQueryContext::get_DefaultDataSource

- ea: `0x2f170`
- end: `0x2f198`
- name: `System.Xml.Xsl.Runtime.XmlQueryContext::get_DefaultDataSource`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x3780`
- `0x2f170`

## string_xrefs

- `0x2f178`: `XmlIl_NoDefaultDocument`

## pseudocode

```c

```

## disassembly

```asm
0x2f170  ldarg.0
0x2f171  ldfld    class [System.Xml]System.Xml.XPath.XPathNavigator System.Xml.Xsl.Runtime.XmlQueryContext::defaultDataSource
0x2f176  brtrue.s loc_2F191
0x2f178  ldstr    aXmlilNodefault// "XmlIl_NoDefaultDocument"
0x2f17d  ldc.i4.1
0x2f17e  newarr   [mscorlib]System.String
0x2f183  dup
0x2f184  ldc.i4.0
0x2f185  ldsfld   string [mscorlib]System.String::Empty
0x2f18a  stelem.ref
0x2f18b  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x2f190  throw
0x2f191  ldarg.0
0x2f192  ldfld    class [System.Xml]System.Xml.XPath.XPathNavigator System.Xml.Xsl.Runtime.XmlQueryContext::defaultDataSource
0x2f197  ret
```
