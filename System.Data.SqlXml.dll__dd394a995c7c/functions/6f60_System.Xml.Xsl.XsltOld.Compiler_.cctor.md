# System.Xml.Xsl.XsltOld.Compiler::.cctor

- ea: `0x6f60`
- end: `0x6fbe`
- name: `System.Xml.Xsl.XsltOld.Compiler::.cctor`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x6f9c`: `System.Xml`
- `0x6fa4`: `System.Xml.Xsl`
- `0x6fac`: `System.Xml.XPath`

## pseudocode

```c

```

## disassembly

```asm
0x6f60  ldstr    asc_580B6// "*"
0x6f65  ldsfld   string [mscorlib]System.String::Empty
0x6f6a  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x6f6f  stsfld   class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.XsltOld.Compiler::BuiltInMode
0x6f74  ldc.i4.7
0x6f75  newarr   [mscorlib]System.String
0x6f7a  dup
0x6f7b  ldc.i4.0
0x6f7c  ldstr    aSystem// "System"
0x6f81  stelem.ref
0x6f82  dup
0x6f83  ldc.i4.1
0x6f84  ldstr    aSystemCollecti// "System.Collections"
0x6f89  stelem.ref
0x6f8a  dup
0x6f8b  ldc.i4.2
0x6f8c  ldstr    aSystemText// "System.Text"
0x6f91  stelem.ref
0x6f92  dup
0x6f93  ldc.i4.3
0x6f94  ldstr    aSystemTextRegu// "System.Text.RegularExpressions"
0x6f99  stelem.ref
0x6f9a  dup
0x6f9b  ldc.i4.4
0x6f9c  ldstr    aSystemXml// "System.Xml"
0x6fa1  stelem.ref
0x6fa2  dup
0x6fa3  ldc.i4.5
0x6fa4  ldstr    aSystemXmlXsl// "System.Xml.Xsl"
0x6fa9  stelem.ref
0x6faa  dup
0x6fab  ldc.i4.6
0x6fac  ldstr    aSystemXmlXpath// "System.Xml.XPath"
0x6fb1  stelem.ref
0x6fb2  stsfld   string[] System.Xml.Xsl.XsltOld.Compiler::_defaultNamespaces
0x6fb7  ldc.i4.0
0x6fb8  stsfld   int32 System.Xml.Xsl.XsltOld.Compiler::scriptClassCounter
0x6fbd  ret
```
