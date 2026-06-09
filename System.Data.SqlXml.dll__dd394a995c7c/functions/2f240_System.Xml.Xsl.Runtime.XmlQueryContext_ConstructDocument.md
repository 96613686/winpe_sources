# System.Xml.Xsl.Runtime.XmlQueryContext::ConstructDocument

- ea: `0x2f240`
- end: `0x2f30c`
- name: `System.Xml.Xsl.Runtime.XmlQueryContext::ConstructDocument`
- size: `204`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x2f090`
- `0x2f1a0`

## callees

- `0x700`
- `0x3780`
- `0x2cf60`
- `0x2f240`

## string_xrefs

- `0x2f2c2`: `XmlIl_CantStripNav`
- `0x2f2e7`: `XmlIl_CantResolveEntity`

## pseudocode

```c

```

## disassembly

```asm
0x2f240  ldarg.1
0x2f241  isinst   [mscorlib]System.IO.Stream
0x2f246  stloc.0
0x2f247  ldloc.0
0x2f248  brfalse.s loc_2F28D
0x2f24a  ldarg.0
0x2f24b  ldfld    class System.Xml.Xsl.QueryReaderSettings System.Xml.Xsl.Runtime.XmlQueryContext::readerSettings
0x2f250  ldloc.0
0x2f251  ldarg.3
0x2f252  ldnull
0x2f253  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x2f258  brtrue.s loc_2F25D
0x2f25a  ldnull
0x2f25b  br.s     loc_2F263
0x2f25d  ldarg.3
0x2f25e  callvirt instance string [mscorlib]System.Object::ToString()
0x2f263  callvirt instance class [System.Xml]System.Xml.XmlReader System.Xml.Xsl.QueryReaderSettings::CreateReader(class [mscorlib]System.IO.Stream stream, string baseUri)
0x2f268  stloc.1
0x2f269  ldloc.1
0x2f26a  ldarg.0
0x2f26b  ldfld    class System.Xml.Xsl.Runtime.WhitespaceRuleLookup System.Xml.Xsl.Runtime.XmlQueryContext::wsRules
0x2f270  call     class [System.Xml]System.Xml.XmlReader System.Xml.Xsl.Runtime.WhitespaceRuleReader::CreateReader(class [System.Xml]System.Xml.XmlReader baseReader, class System.Xml.Xsl.Runtime.WhitespaceRuleLookup wsRules)
0x2f275  ldc.i4.2
0x2f276  newobj   instance void [System.Xml]System.Xml.XPath.XPathDocument::.ctor(class [System.Xml]System.Xml.XmlReader, valuetype [System.Xml]System.Xml.XmlSpace)
0x2f27b  call     instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathDocument::CreateNavigator()
0x2f280  stloc.2
0x2f281  leave    loc_2F30A
0x2f286  ldloc.1
0x2f287  callvirt instance void [System.Xml]System.Xml.XmlReader::Close()
0x2f28c  endfinally
0x2f28d  ldarg.1
0x2f28e  isinst   [System.Xml]System.Xml.XmlReader
0x2f293  brfalse.s loc_2F2B2
0x2f295  ldarg.1
0x2f296  isinst   [System.Xml]System.Xml.XmlReader
0x2f29b  ldarg.0
0x2f29c  ldfld    class System.Xml.Xsl.Runtime.WhitespaceRuleLookup System.Xml.Xsl.Runtime.XmlQueryContext::wsRules
0x2f2a1  call     class [System.Xml]System.Xml.XmlReader System.Xml.Xsl.Runtime.WhitespaceRuleReader::CreateReader(class [System.Xml]System.Xml.XmlReader baseReader, class System.Xml.Xsl.Runtime.WhitespaceRuleLookup wsRules)
0x2f2a6  ldc.i4.2
0x2f2a7  newobj   instance void [System.Xml]System.Xml.XPath.XPathDocument::.ctor(class [System.Xml]System.Xml.XmlReader, valuetype [System.Xml]System.Xml.XmlSpace)
0x2f2ac  call     instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathDocument::CreateNavigator()
0x2f2b1  ret
0x2f2b2  ldarg.1
0x2f2b3  isinst   [System.Xml]System.Xml.XPath.IXPathNavigable
0x2f2b8  brfalse.s loc_2F2E7
0x2f2ba  ldarg.0
0x2f2bb  ldfld    class System.Xml.Xsl.Runtime.WhitespaceRuleLookup System.Xml.Xsl.Runtime.XmlQueryContext::wsRules
0x2f2c0  brfalse.s loc_2F2DB
0x2f2c2  ldstr    aXmlilCantstrip// "XmlIl_CantStripNav"
0x2f2c7  ldc.i4.1
0x2f2c8  newarr   [mscorlib]System.String
0x2f2cd  dup
0x2f2ce  ldc.i4.0
0x2f2cf  ldsfld   string [mscorlib]System.String::Empty
0x2f2d4  stelem.ref
0x2f2d5  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x2f2da  throw
0x2f2db  ldarg.1
0x2f2dc  isinst   [System.Xml]System.Xml.XPath.IXPathNavigable
0x2f2e1  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.IXPathNavigable::CreateNavigator()
0x2f2e6  ret
0x2f2e7  ldstr    aXmlilCantresol// "XmlIl_CantResolveEntity"
0x2f2ec  ldc.i4.2
0x2f2ed  newarr   [mscorlib]System.String
0x2f2f2  dup
0x2f2f3  ldc.i4.0
0x2f2f4  ldarg.2
0x2f2f5  stelem.ref
0x2f2f6  dup
0x2f2f7  ldc.i4.1
0x2f2f8  ldarg.1
0x2f2f9  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2f2fe  callvirt instance string [mscorlib]System.Object::ToString()
0x2f303  stelem.ref
0x2f304  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x2f309  throw
0x2f30a  ldloc.2
0x2f30b  ret
```
