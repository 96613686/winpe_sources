# System.Xml.XmlWellFormedWriter::PushNamespaceExplicit

- ea: `0x3e110`
- end: `0x3e2e5`
- name: `System.Xml.XmlWellFormedWriter::PushNamespaceExplicit`
- size: `469`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x3d180`
- `0x111a90`

## callees

- `0xe330`
- `0x12660`
- `0x3e110`
- `0x3e2f0`
- `0x3e3e0`
- `0x3e4a0`
- `0x622f0`
- `0x62370`

## string_xrefs

- `0x3e232`: `http://www.w3.org/XML/1998/namespace`
- `0x3e2a1`: `http://www.w3.org/XML/1998/namespace`
- `0x3e24c`: `http://www.w3.org/2000/xmlns/`
- `0x3e1a0`: `xmlns`
- `0x3e1b7`: `xmlns`
- `0x3e259`: `xmlns`
- `0x3e2be`: `xmlns`
- `0x3e2ad`: `Xml_XmlPrefix`
- `0x3e2ca`: `Xml_XmlnsPrefix`
- `0x3e265`: `Xml_NamespaceDeclXmlXmlns`
- `0x3e156`: `Xml_RedefinePrefix`

## pseudocode

```c

```

## disassembly

```asm
0x3e110  ldc.i4.1
0x3e111  stloc.0
0x3e112  ldarg.0
0x3e113  ldarg.1
0x3e114  call     instance int32 System.Xml.XmlWellFormedWriter::LookupNamespaceIndex(string prefix)
0x3e119  stloc.1
0x3e11a  ldloc.1
0x3e11b  ldc.i4.m1
0x3e11c  beq      loc_3E209
0x3e121  ldloc.1
0x3e122  ldarg.0
0x3e123  ldfld    valuetype ElementScope[] System.Xml.XmlWellFormedWriter::elemScopeStack
0x3e128  ldarg.0
0x3e129  ldfld    int32 System.Xml.XmlWellFormedWriter::elemTop
0x3e12e  ldelema  ElementScope
0x3e133  ldfld    int32 ElementScope::prevNSTop
0x3e138  ble      loc_3E1E4
0x3e13d  ldarg.0
0x3e13e  ldfld    valuetype Namespace[] System.Xml.XmlWellFormedWriter::nsStack
0x3e143  ldloc.1
0x3e144  ldelema  Namespace
0x3e149  ldfld    string Namespace::namespaceUri
0x3e14e  ldarg.2
0x3e14f  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3e154  brfalse.s loc_3E183
0x3e156  ldstr    aXmlRedefinepre// "Xml_RedefinePrefix"
0x3e15b  ldc.i4.3
0x3e15c  newarr   [mscorlib]System.String
0x3e161  dup
0x3e162  ldc.i4.0
0x3e163  ldarg.1
0x3e164  stelem.ref
0x3e165  dup
0x3e166  ldc.i4.1
0x3e167  ldarg.0
0x3e168  ldfld    valuetype Namespace[] System.Xml.XmlWellFormedWriter::nsStack
0x3e16d  ldloc.1
0x3e16e  ldelema  Namespace
0x3e173  ldfld    string Namespace::namespaceUri
0x3e178  stelem.ref
0x3e179  dup
0x3e17a  ldc.i4.2
0x3e17b  ldarg.2
0x3e17c  stelem.ref
0x3e17d  newobj   instance void System.Xml.XmlException::.ctor(string res, string[] args)
0x3e182  throw
0x3e183  ldarg.0
0x3e184  ldfld    valuetype Namespace[] System.Xml.XmlWellFormedWriter::nsStack
0x3e189  ldloc.1
0x3e18a  ldelema  Namespace
0x3e18f  ldfld    valuetype NamespaceKind Namespace::kind
0x3e194  stloc.2
0x3e195  ldloc.2
0x3e196  brtrue.s loc_3E1C2
0x3e198  ldarg.1
0x3e199  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3e19e  brfalse.s loc_3E1A7
0x3e1a0  ldstr    aXmlns// "xmlns"
0x3e1a5  br.s     loc_3E1AC
0x3e1a7  ldsfld   string [mscorlib]System.String::Empty
0x3e1ac  ldarg.1
0x3e1ad  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3e1b2  brfalse.s loc_3E1B7
0x3e1b4  ldarg.1
0x3e1b5  br.s     loc_3E1BC
0x3e1b7  ldstr    aXmlns// "xmlns"
0x3e1bc  call     class System.Xml.XmlException System.Xml.XmlWellFormedWriter::DupAttrException(string prefix, string localName)
0x3e1c1  throw
0x3e1c2  ldarg.0
0x3e1c3  ldfld    bool System.Xml.XmlWellFormedWriter::omitDuplNamespaces
0x3e1c8  brfalse.s loc_3E1D0
0x3e1ca  ldloc.2
0x3e1cb  ldc.i4.1
0x3e1cc  beq.s    loc_3E1D0
0x3e1ce  ldc.i4.0
0x3e1cf  stloc.0
0x3e1d0  ldarg.0
0x3e1d1  ldfld    valuetype Namespace[] System.Xml.XmlWellFormedWriter::nsStack
0x3e1d6  ldloc.1
0x3e1d7  ldelema  Namespace
0x3e1dc  ldc.i4.0
0x3e1dd  stfld    valuetype NamespaceKind Namespace::kind
0x3e1e2  ldloc.0
0x3e1e3  ret
0x3e1e4  ldarg.0
0x3e1e5  ldfld    valuetype Namespace[] System.Xml.XmlWellFormedWriter::nsStack
0x3e1ea  ldloc.1
0x3e1eb  ldelema  Namespace
0x3e1f0  ldfld    string Namespace::namespaceUri
0x3e1f5  ldarg.2
0x3e1f6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e1fb  brfalse.s loc_3E231
0x3e1fd  ldarg.0
0x3e1fe  ldfld    bool System.Xml.XmlWellFormedWriter::omitDuplNamespaces
0x3e203  brfalse.s loc_3E231
0x3e205  ldc.i4.0
0x3e206  stloc.0
0x3e207  br.s     loc_3E231
0x3e209  ldarg.0
0x3e20a  ldfld    class System.Xml.IXmlNamespaceResolver System.Xml.XmlWellFormedWriter::predefinedNamespaces
0x3e20f  brfalse.s loc_3E231
0x3e211  ldarg.0
0x3e212  ldfld    class System.Xml.IXmlNamespaceResolver System.Xml.XmlWellFormedWriter::predefinedNamespaces
0x3e217  ldarg.1
0x3e218  callvirt instance string System.Xml.IXmlNamespaceResolver::LookupNamespace(string prefix)
0x3e21d  stloc.3
0x3e21e  ldloc.3
0x3e21f  ldarg.2
0x3e220  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e225  brfalse.s loc_3E231
0x3e227  ldarg.0
0x3e228  ldfld    bool System.Xml.XmlWellFormedWriter::omitDuplNamespaces
0x3e22d  brfalse.s loc_3E231
0x3e22f  ldc.i4.0
0x3e230  stloc.0
0x3e231  ldarg.2
0x3e232  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x3e237  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e23c  brfalse.s loc_3E24B
0x3e23e  ldarg.1
0x3e23f  ldstr    aXml// "xml"
0x3e244  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3e249  brtrue.s loc_3E265
0x3e24b  ldarg.2
0x3e24c  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x3e251  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e256  brfalse.s loc_3E27F
0x3e258  ldarg.1
0x3e259  ldstr    aXmlns// "xmlns"
0x3e25e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3e263  brfalse.s loc_3E27F
0x3e265  ldstr    aXmlNamespacede// "Xml_NamespaceDeclXmlXmlns"
0x3e26a  ldc.i4.1
0x3e26b  newarr   [mscorlib]System.Object
0x3e270  dup
0x3e271  ldc.i4.0
0x3e272  ldarg.1
0x3e273  stelem.ref
0x3e274  call     string System.Xml.Res::GetString(string name, object[] args)
0x3e279  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3e27e  throw
0x3e27f  ldarg.1
0x3e280  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3e285  ldc.i4.0
0x3e286  ble.s    loc_3E2DA
0x3e288  ldarg.1
0x3e289  ldc.i4.0
0x3e28a  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3e28f  ldc.i4.s 0x78
0x3e291  bne.un.s loc_3E2DA
0x3e293  ldarg.1
0x3e294  ldstr    aXml// "xml"
0x3e299  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e29e  brfalse.s loc_3E2BD
0x3e2a0  ldarg.2
0x3e2a1  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x3e2a6  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3e2ab  brfalse.s loc_3E2DA
0x3e2ad  ldstr    aXmlXmlprefix// "Xml_XmlPrefix"
0x3e2b2  call     string System.Xml.Res::GetString(string name)
0x3e2b7  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3e2bc  throw
0x3e2bd  ldarg.1
0x3e2be  ldstr    aXmlns// "xmlns"
0x3e2c3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e2c8  brfalse.s loc_3E2DA
0x3e2ca  ldstr    aXmlXmlnsprefix// "Xml_XmlnsPrefix"
0x3e2cf  call     string System.Xml.Res::GetString(string name)
0x3e2d4  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3e2d9  throw
0x3e2da  ldarg.0
0x3e2db  ldarg.1
0x3e2dc  ldarg.2
0x3e2dd  ldc.i4.0
0x3e2de  call     instance void System.Xml.XmlWellFormedWriter::AddNamespace(string prefix, string ns, valuetype NamespaceKind kind)
0x3e2e3  ldloc.0
0x3e2e4  ret
```
