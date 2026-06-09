# System.Xml.XmlWellFormedWriter::.ctor

- ea: `0x3c850`
- end: `0x3ca09`
- name: `System.Xml.XmlWellFormedWriter::.ctor`
- size: `441`
- prototype: ``
- caller_count: `9`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x41b90`
- `0x41ce0`
- `0x41ec0`
- `0x48370`
- `0x483e0`
- `0x48450`
- `0x484f0`
- `0x48590`
- `0x485f0`

## callees

- `0xe330`
- `0xef20`
- `0x17930`
- `0x21100`
- `0x3c850`
- `0x415c0`
- `0x41830`
- `0x41870`
- `0x418a0`
- `0x418e0`
- `0x110590`
- `0x1105e0`
- `0x1106b0`

## string_xrefs

- `0x3c929`: `http://www.w3.org/XML/1998/namespace`
- `0x3c90d`: `http://www.w3.org/2000/xmlns/`
- `0x3c908`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0x3c850  ldarg.0
0x3c851  call     valuetype System.Xml.XmlCharType System.Xml.XmlCharType::get_Instance()
0x3c856  stfld    valuetype System.Xml.XmlCharType System.Xml.XmlWellFormedWriter::xmlCharType
0x3c85b  ldarg.0
0x3c85c  call     instance void System.Xml.XmlWriter::.ctor()
0x3c861  ldarg.0
0x3c862  ldarg.1
0x3c863  stfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x3c868  ldarg.0
0x3c869  ldarg.1
0x3c86a  isinst   System.Xml.XmlRawWriter
0x3c86f  stfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x3c874  ldarg.0
0x3c875  ldarg.1
0x3c876  isinst   System.Xml.IXmlNamespaceResolver
0x3c87b  stfld    class System.Xml.IXmlNamespaceResolver System.Xml.XmlWellFormedWriter::predefinedNamespaces
0x3c880  ldarg.0
0x3c881  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x3c886  brfalse.s loc_3C899
0x3c888  ldarg.0
0x3c889  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x3c88e  ldarg.0
0x3c88f  newobj   instance void NamespaceResolverProxy::.ctor(class System.Xml.XmlWellFormedWriter wfWriter)
0x3c894  callvirt instance void System.Xml.XmlRawWriter::set_NamespaceResolver(class System.Xml.IXmlNamespaceResolver value)
0x3c899  ldarg.0
0x3c89a  ldarg.2
0x3c89b  callvirt instance bool System.Xml.XmlWriterSettings::get_CheckCharacters()
0x3c8a0  stfld    bool System.Xml.XmlWellFormedWriter::checkCharacters
0x3c8a5  ldarg.0
0x3c8a6  ldarg.2
0x3c8a7  callvirt instance valuetype System.Xml.NamespaceHandling System.Xml.XmlWriterSettings::get_NamespaceHandling()
0x3c8ac  ldc.i4.1
0x3c8ad  and
0x3c8ae  ldc.i4.0
0x3c8af  cgt.un
0x3c8b1  stfld    bool System.Xml.XmlWellFormedWriter::omitDuplNamespaces
0x3c8b6  ldarg.0
0x3c8b7  ldarg.2
0x3c8b8  callvirt instance bool System.Xml.XmlWriterSettings::get_WriteEndDocumentOnClose()
0x3c8bd  stfld    bool System.Xml.XmlWellFormedWriter::writeEndDocumentOnClose
0x3c8c2  ldarg.0
0x3c8c3  ldarg.2
0x3c8c4  callvirt instance valuetype System.Xml.ConformanceLevel System.Xml.XmlWriterSettings::get_ConformanceLevel()
0x3c8c9  stfld    valuetype System.Xml.ConformanceLevel System.Xml.XmlWellFormedWriter::conformanceLevel
0x3c8ce  ldarg.0
0x3c8cf  ldarg.0
0x3c8d0  ldfld    valuetype System.Xml.ConformanceLevel System.Xml.XmlWellFormedWriter::conformanceLevel
0x3c8d5  ldc.i4.2
0x3c8d6  beq.s    loc_3C8DF
0x3c8d8  ldsfld   valuetype State[] System.Xml.XmlWellFormedWriter::StateTableAuto
0x3c8dd  br.s     loc_3C8E4
0x3c8df  ldsfld   valuetype State[] System.Xml.XmlWellFormedWriter::StateTableDocument
0x3c8e4  stfld    valuetype State[] System.Xml.XmlWellFormedWriter::stateTable
0x3c8e9  ldarg.0
0x3c8ea  ldc.i4.0
0x3c8eb  stfld    valuetype State System.Xml.XmlWellFormedWriter::currentState
0x3c8f0  ldarg.0
0x3c8f1  ldc.i4.8
0x3c8f2  newarr   Namespace
0x3c8f7  stfld    valuetype Namespace[] System.Xml.XmlWellFormedWriter::nsStack
0x3c8fc  ldarg.0
0x3c8fd  ldfld    valuetype Namespace[] System.Xml.XmlWellFormedWriter::nsStack
0x3c902  ldc.i4.0
0x3c903  ldelema  Namespace
0x3c908  ldstr    aXmlns// "xmlns"
0x3c90d  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x3c912  ldc.i4.3
0x3c913  call     instance void Namespace::Set(string prefix, string namespaceUri, valuetype NamespaceKind kind)
0x3c918  ldarg.0
0x3c919  ldfld    valuetype Namespace[] System.Xml.XmlWellFormedWriter::nsStack
0x3c91e  ldc.i4.1
0x3c91f  ldelema  Namespace
0x3c924  ldstr    aXml// "xml"
0x3c929  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x3c92e  ldc.i4.3
0x3c92f  call     instance void Namespace::Set(string prefix, string namespaceUri, valuetype NamespaceKind kind)
0x3c934  ldarg.0
0x3c935  ldfld    class System.Xml.IXmlNamespaceResolver System.Xml.XmlWellFormedWriter::predefinedNamespaces
0x3c93a  brtrue.s loc_3C95A
0x3c93c  ldarg.0
0x3c93d  ldfld    valuetype Namespace[] System.Xml.XmlWellFormedWriter::nsStack
0x3c942  ldc.i4.2
0x3c943  ldelema  Namespace
0x3c948  ldsfld   string [mscorlib]System.String::Empty
0x3c94d  ldsfld   string [mscorlib]System.String::Empty
0x3c952  ldc.i4.2
0x3c953  call     instance void Namespace::Set(string prefix, string namespaceUri, valuetype NamespaceKind kind)
0x3c958  br.s     loc_3C98D
0x3c95a  ldarg.0
0x3c95b  ldfld    class System.Xml.IXmlNamespaceResolver System.Xml.XmlWellFormedWriter::predefinedNamespaces
0x3c960  ldsfld   string [mscorlib]System.String::Empty
0x3c965  callvirt instance string System.Xml.IXmlNamespaceResolver::LookupNamespace(string prefix)
0x3c96a  stloc.0
0x3c96b  ldarg.0
0x3c96c  ldfld    valuetype Namespace[] System.Xml.XmlWellFormedWriter::nsStack
0x3c971  ldc.i4.2
0x3c972  ldelema  Namespace
0x3c977  ldsfld   string [mscorlib]System.String::Empty
0x3c97c  ldloc.0
0x3c97d  brfalse.s loc_3C982
0x3c97f  ldloc.0
0x3c980  br.s     loc_3C987
0x3c982  ldsfld   string [mscorlib]System.String::Empty
0x3c987  ldc.i4.2
0x3c988  call     instance void Namespace::Set(string prefix, string namespaceUri, valuetype NamespaceKind kind)
0x3c98d  ldarg.0
0x3c98e  ldc.i4.2
0x3c98f  stfld    int32 System.Xml.XmlWellFormedWriter::nsTop
0x3c994  ldarg.0
0x3c995  ldc.i4.8
0x3c996  newarr   ElementScope
0x3c99b  stfld    valuetype ElementScope[] System.Xml.XmlWellFormedWriter::elemScopeStack
0x3c9a0  ldarg.0
0x3c9a1  ldfld    valuetype ElementScope[] System.Xml.XmlWellFormedWriter::elemScopeStack
0x3c9a6  ldc.i4.0
0x3c9a7  ldelema  ElementScope
0x3c9ac  ldsfld   string [mscorlib]System.String::Empty
0x3c9b1  ldsfld   string [mscorlib]System.String::Empty
0x3c9b6  ldsfld   string [mscorlib]System.String::Empty
0x3c9bb  ldarg.0
0x3c9bc  ldfld    int32 System.Xml.XmlWellFormedWriter::nsTop
0x3c9c1  call     instance void ElementScope::Set(string prefix, string localName, string namespaceUri, int32 prevNSTop)
0x3c9c6  ldarg.0
0x3c9c7  ldfld    valuetype ElementScope[] System.Xml.XmlWellFormedWriter::elemScopeStack
0x3c9cc  ldc.i4.0
0x3c9cd  ldelema  ElementScope
0x3c9d2  ldc.i4.0
0x3c9d3  stfld    valuetype System.Xml.XmlSpace ElementScope::xmlSpace
0x3c9d8  ldarg.0
0x3c9d9  ldfld    valuetype ElementScope[] System.Xml.XmlWellFormedWriter::elemScopeStack
0x3c9de  ldc.i4.0
0x3c9df  ldelema  ElementScope
0x3c9e4  ldnull
0x3c9e5  stfld    string ElementScope::xmlLang
0x3c9ea  ldarg.0
0x3c9eb  ldc.i4.0
0x3c9ec  stfld    int32 System.Xml.XmlWellFormedWriter::elemTop
0x3c9f1  ldarg.0
0x3c9f2  ldc.i4.8
0x3c9f3  newarr   AttrName
0x3c9f8  stfld    valuetype AttrName[] System.Xml.XmlWellFormedWriter::attrStack
0x3c9fd  ldarg.0
0x3c9fe  newobj   instance void System.Xml.SecureStringHasher::.ctor()
0x3ca03  stfld    class System.Xml.SecureStringHasher System.Xml.XmlWellFormedWriter::hasher
0x3ca08  ret
```
