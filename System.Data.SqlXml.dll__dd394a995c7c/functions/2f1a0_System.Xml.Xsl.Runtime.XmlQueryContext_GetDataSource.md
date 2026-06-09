# System.Xml.Xsl.Runtime.XmlQueryContext::GetDataSource

- ea: `0x2f1a0`
- end: `0x2f236`
- name: `System.Xml.Xsl.Runtime.XmlQueryContext::GetDataSource`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x2f090`

## callees

- `0x3760`
- `0x2f1a0`
- `0x2f240`

## string_xrefs

- `0x2f21f`: `XmlIl_DocumentLoadError`

## pseudocode

```c

```

## disassembly

```asm
0x2f1a0  ldnull
0x2f1a1  stloc.3
0x2f1a2  ldarg.2
0x2f1a3  brtrue.s loc_2F1A8
0x2f1a5  ldnull
0x2f1a6  br.s     loc_2F1B5
0x2f1a8  ldarg.0
0x2f1a9  ldfld    class [System.Xml]System.Xml.XmlResolver System.Xml.Xsl.Runtime.XmlQueryContext::dataSources
0x2f1ae  ldnull
0x2f1af  ldarg.2
0x2f1b0  callvirt instance class [System]System.Uri [System.Xml]System.Xml.XmlResolver::ResolveUri(class [System]System.Uri, string)
0x2f1b5  stloc.1
0x2f1b6  ldarg.0
0x2f1b7  ldfld    class [System.Xml]System.Xml.XmlResolver System.Xml.Xsl.Runtime.XmlQueryContext::dataSources
0x2f1bc  ldloc.1
0x2f1bd  ldarg.1
0x2f1be  callvirt instance class [System]System.Uri [System.Xml]System.Xml.XmlResolver::ResolveUri(class [System]System.Uri, string)
0x2f1c3  stloc.2
0x2f1c4  ldloc.2
0x2f1c5  ldnull
0x2f1c6  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x2f1cb  brfalse.s loc_2F1DF
0x2f1cd  ldarg.0
0x2f1ce  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.Runtime.XmlQueryContext::dataSourceCache
0x2f1d3  ldloc.2
0x2f1d4  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x2f1d9  isinst   [System.Xml]System.Xml.XPath.XPathNavigator
0x2f1de  stloc.3
0x2f1df  ldloc.3
0x2f1e0  brtrue.s loc_2F20B
0x2f1e2  ldarg.0
0x2f1e3  ldfld    class [System.Xml]System.Xml.XmlResolver System.Xml.Xsl.Runtime.XmlQueryContext::dataSources
0x2f1e8  ldloc.2
0x2f1e9  ldnull
0x2f1ea  ldnull
0x2f1eb  callvirt instance object [System.Xml]System.Xml.XmlResolver::GetEntity(class [System]System.Uri, string, class [mscorlib]System.Type)
0x2f1f0  stloc.0
0x2f1f1  ldloc.0
0x2f1f2  brfalse.s loc_2F20B
0x2f1f4  ldarg.0
0x2f1f5  ldloc.0
0x2f1f6  ldarg.1
0x2f1f7  ldloc.2
0x2f1f8  call     instance class [System.Xml]System.Xml.XPath.XPathNavigator System.Xml.Xsl.Runtime.XmlQueryContext::ConstructDocument(object dataSource, string uriRelative, class [System]System.Uri uriResolved)
0x2f1fd  stloc.3
0x2f1fe  ldarg.0
0x2f1ff  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.Runtime.XmlQueryContext::dataSourceCache
0x2f204  ldloc.2
0x2f205  ldloc.3
0x2f206  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x2f20b  leave.s  loc_2F234
0x2f20d  pop
0x2f20e  rethrow
0x2f210  stloc.s  4
0x2f212  ldloc.s  4
0x2f214  call     bool [System.Xml]System.Xml.XmlException::IsCatchableException(class [mscorlib]System.Exception)
0x2f219  brtrue.s loc_2F21D
0x2f21b  rethrow
0x2f21d  ldloc.s  4
0x2f21f  ldstr    aXmlilDocumentl// "XmlIl_DocumentLoadError"
0x2f224  ldc.i4.1
0x2f225  newarr   [mscorlib]System.String
0x2f22a  dup
0x2f22b  ldc.i4.0
0x2f22c  ldarg.1
0x2f22d  stelem.ref
0x2f22e  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(class [mscorlib]System.Exception inner, string res, string[] args)
0x2f233  throw
0x2f234  ldloc.3
0x2f235  ret
```
