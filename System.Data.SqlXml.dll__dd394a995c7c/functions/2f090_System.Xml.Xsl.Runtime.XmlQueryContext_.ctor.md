# System.Xml.Xsl.Runtime.XmlQueryContext::.ctor

- ea: `0x2f090`
- end: `0x2f13a`
- name: `System.Xml.Xsl.Runtime.XmlQueryContext::.ctor`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x30880`

## callees

- `0x570`
- `0x5c0`
- `0x3780`
- `0x2f090`
- `0x2f1a0`
- `0x2f240`

## string_xrefs

- `0x2f10d`: `XmlIl_UnknownDocument`

## pseudocode

```c

```

## disassembly

```asm
0x2f090  ldarg.0
0x2f091  call     instance void [mscorlib]System.Object::.ctor()
0x2f096  ldarg.0
0x2f097  ldarg.1
0x2f098  stfld    class System.Xml.Xsl.Runtime.XmlQueryRuntime System.Xml.Xsl.Runtime.XmlQueryContext::runtime
0x2f09d  ldarg.0
0x2f09e  ldarg.3
0x2f09f  stfld    class [System.Xml]System.Xml.XmlResolver System.Xml.Xsl.Runtime.XmlQueryContext::dataSources
0x2f0a4  ldarg.0
0x2f0a5  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x2f0aa  stfld    class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.Runtime.XmlQueryContext::dataSourceCache
0x2f0af  ldarg.0
0x2f0b0  ldarg.s  4
0x2f0b2  stfld    class [System.Xml]System.Xml.Xsl.XsltArgumentList System.Xml.Xsl.Runtime.XmlQueryContext::argList
0x2f0b7  ldarg.0
0x2f0b8  ldarg.s  5
0x2f0ba  stfld    class System.Xml.Xsl.Runtime.WhitespaceRuleLookup System.Xml.Xsl.Runtime.XmlQueryContext::wsRules
0x2f0bf  ldarg.2
0x2f0c0  isinst   [System.Xml]System.Xml.XmlReader
0x2f0c5  brfalse.s loc_2F0DA
0x2f0c7  ldarg.0
0x2f0c8  ldarg.2
0x2f0c9  castclass [System.Xml]System.Xml.XmlReader
0x2f0ce  newobj   instance void System.Xml.Xsl.QueryReaderSettings::.ctor(class [System.Xml]System.Xml.XmlReader reader)
0x2f0d3  stfld    class System.Xml.Xsl.QueryReaderSettings System.Xml.Xsl.Runtime.XmlQueryContext::readerSettings
0x2f0d8  br.s     loc_2F0EA
0x2f0da  ldarg.0
0x2f0db  newobj   instance void [System.Xml]System.Xml.NameTable::.ctor()
0x2f0e0  newobj   instance void System.Xml.Xsl.QueryReaderSettings::.ctor(class [System.Xml]System.Xml.XmlNameTable xmlNameTable)
0x2f0e5  stfld    class System.Xml.Xsl.QueryReaderSettings System.Xml.Xsl.Runtime.XmlQueryContext::readerSettings
0x2f0ea  ldarg.2
0x2f0eb  isinst   [mscorlib]System.String
0x2f0f0  brfalse.s loc_2F127
0x2f0f2  ldarg.0
0x2f0f3  ldarg.0
0x2f0f4  ldarg.2
0x2f0f5  isinst   [mscorlib]System.String
0x2f0fa  ldnull
0x2f0fb  call     instance class [System.Xml]System.Xml.XPath.XPathNavigator System.Xml.Xsl.Runtime.XmlQueryContext::GetDataSource(string uriRelative, string uriBase)
0x2f100  stfld    class [System.Xml]System.Xml.XPath.XPathNavigator System.Xml.Xsl.Runtime.XmlQueryContext::defaultDataSource
0x2f105  ldarg.0
0x2f106  ldfld    class [System.Xml]System.Xml.XPath.XPathNavigator System.Xml.Xsl.Runtime.XmlQueryContext::defaultDataSource
0x2f10b  brtrue.s loc_2F139
0x2f10d  ldstr    aXmlilUnknowndo// "XmlIl_UnknownDocument"
0x2f112  ldc.i4.1
0x2f113  newarr   [mscorlib]System.String
0x2f118  dup
0x2f119  ldc.i4.0
0x2f11a  ldarg.2
0x2f11b  isinst   [mscorlib]System.String
0x2f120  stelem.ref
0x2f121  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x2f126  throw
0x2f127  ldarg.2
0x2f128  brfalse.s loc_2F139
0x2f12a  ldarg.0
0x2f12b  ldarg.0
0x2f12c  ldarg.2
0x2f12d  ldnull
0x2f12e  ldnull
0x2f12f  call     instance class [System.Xml]System.Xml.XPath.XPathNavigator System.Xml.Xsl.Runtime.XmlQueryContext::ConstructDocument(object dataSource, string uriRelative, class [System]System.Uri uriResolved)
0x2f134  stfld    class [System.Xml]System.Xml.XPath.XPathNavigator System.Xml.Xsl.Runtime.XmlQueryContext::defaultDataSource
0x2f139  ret
```
