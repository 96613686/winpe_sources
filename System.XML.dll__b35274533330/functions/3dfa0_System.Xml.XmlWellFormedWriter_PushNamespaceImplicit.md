# System.Xml.XmlWellFormedWriter::PushNamespaceImplicit

- ea: `0x3dfa0`
- end: `0x3e10f`
- name: `System.Xml.XmlWellFormedWriter::PushNamespaceImplicit`
- size: `367`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x3cc50`
- `0x3cf20`
- `0x3db50`
- `0x3ee60`
- `0x3f190`
- `0x113be0`

## callees

- `0xe330`
- `0x12660`
- `0x3dfa0`
- `0x3e2f0`
- `0x3e3e0`
- `0x622f0`
- `0x62370`

## string_xrefs

- `0x3e091`: `http://www.w3.org/XML/1998/namespace`
- `0x3e0ab`: `http://www.w3.org/2000/xmlns/`
- `0x3e0b8`: `xmlns`
- `0x3e049`: `Xml_XmlPrefix`
- `0x3e060`: `Xml_XmlnsPrefix`
- `0x3e0c4`: `Xml_NamespaceDeclXmlXmlns`
- `0x3dfe1`: `Xml_RedefinePrefix`

## pseudocode

```c

```

## disassembly

```asm
0x3dfa0  ldarg.0
0x3dfa1  ldarg.1
0x3dfa2  call     instance int32 System.Xml.XmlWellFormedWriter::LookupNamespaceIndex(string prefix)
0x3dfa7  stloc.1
0x3dfa8  ldloc.1
0x3dfa9  ldc.i4.m1
0x3dfaa  beq      loc_3E090
0x3dfaf  ldloc.1
0x3dfb0  ldarg.0
0x3dfb1  ldfld    valuetype ElementScope[] System.Xml.XmlWellFormedWriter::elemScopeStack
0x3dfb6  ldarg.0
0x3dfb7  ldfld    int32 System.Xml.XmlWellFormedWriter::elemTop
0x3dfbc  ldelema  ElementScope
0x3dfc1  ldfld    int32 ElementScope::prevNSTop
0x3dfc6  ble.s    loc_3E00F
0x3dfc8  ldarg.0
0x3dfc9  ldfld    valuetype Namespace[] System.Xml.XmlWellFormedWriter::nsStack
0x3dfce  ldloc.1
0x3dfcf  ldelema  Namespace
0x3dfd4  ldfld    string Namespace::namespaceUri
0x3dfd9  ldarg.2
0x3dfda  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3dfdf  brfalse.s loc_3E00E
0x3dfe1  ldstr    aXmlRedefinepre// "Xml_RedefinePrefix"
0x3dfe6  ldc.i4.3
0x3dfe7  newarr   [mscorlib]System.String
0x3dfec  dup
0x3dfed  ldc.i4.0
0x3dfee  ldarg.1
0x3dfef  stelem.ref
0x3dff0  dup
0x3dff1  ldc.i4.1
0x3dff2  ldarg.0
0x3dff3  ldfld    valuetype Namespace[] System.Xml.XmlWellFormedWriter::nsStack
0x3dff8  ldloc.1
0x3dff9  ldelema  Namespace
0x3dffe  ldfld    string Namespace::namespaceUri
0x3e003  stelem.ref
0x3e004  dup
0x3e005  ldc.i4.2
0x3e006  ldarg.2
0x3e007  stelem.ref
0x3e008  newobj   instance void System.Xml.XmlException::.ctor(string res, string[] args)
0x3e00d  throw
0x3e00e  ret
0x3e00f  ldarg.0
0x3e010  ldfld    valuetype Namespace[] System.Xml.XmlWellFormedWriter::nsStack
0x3e015  ldloc.1
0x3e016  ldelema  Namespace
0x3e01b  ldfld    valuetype NamespaceKind Namespace::kind
0x3e020  ldc.i4.3
0x3e021  bne.un.s loc_3E070
0x3e023  ldarg.1
0x3e024  ldstr    aXml// "xml"
0x3e029  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e02e  brfalse.s loc_3E060
0x3e030  ldarg.2
0x3e031  ldarg.0
0x3e032  ldfld    valuetype Namespace[] System.Xml.XmlWellFormedWriter::nsStack
0x3e037  ldloc.1
0x3e038  ldelema  Namespace
0x3e03d  ldfld    string Namespace::namespaceUri
0x3e042  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3e047  brfalse.s loc_3E059
0x3e049  ldstr    aXmlXmlprefix// "Xml_XmlPrefix"
0x3e04e  call     string System.Xml.Res::GetString(string name)
0x3e053  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3e058  throw
0x3e059  ldc.i4.2
0x3e05a  stloc.0
0x3e05b  br       loc_3E105
0x3e060  ldstr    aXmlXmlnsprefix// "Xml_XmlnsPrefix"
0x3e065  call     string System.Xml.Res::GetString(string name)
0x3e06a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3e06f  throw
0x3e070  ldarg.0
0x3e071  ldfld    valuetype Namespace[] System.Xml.XmlWellFormedWriter::nsStack
0x3e076  ldloc.1
0x3e077  ldelema  Namespace
0x3e07c  ldfld    string Namespace::namespaceUri
0x3e081  ldarg.2
0x3e082  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e087  brtrue.s loc_3E08C
0x3e089  ldc.i4.1
0x3e08a  br.s     loc_3E08D
0x3e08c  ldc.i4.2
0x3e08d  stloc.0
0x3e08e  br.s     loc_3E105
0x3e090  ldarg.2
0x3e091  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x3e096  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e09b  brfalse.s loc_3E0AA
0x3e09d  ldarg.1
0x3e09e  ldstr    aXml// "xml"
0x3e0a3  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3e0a8  brtrue.s loc_3E0C4
0x3e0aa  ldarg.2
0x3e0ab  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x3e0b0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e0b5  brfalse.s loc_3E0DE
0x3e0b7  ldarg.1
0x3e0b8  ldstr    aXmlns// "xmlns"
0x3e0bd  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3e0c2  brfalse.s loc_3E0DE
0x3e0c4  ldstr    aXmlNamespacede// "Xml_NamespaceDeclXmlXmlns"
0x3e0c9  ldc.i4.1
0x3e0ca  newarr   [mscorlib]System.Object
0x3e0cf  dup
0x3e0d0  ldc.i4.0
0x3e0d1  ldarg.1
0x3e0d2  stelem.ref
0x3e0d3  call     string System.Xml.Res::GetString(string name, object[] args)
0x3e0d8  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3e0dd  throw
0x3e0de  ldarg.0
0x3e0df  ldfld    class System.Xml.IXmlNamespaceResolver System.Xml.XmlWellFormedWriter::predefinedNamespaces
0x3e0e4  brfalse.s loc_3E103
0x3e0e6  ldarg.0
0x3e0e7  ldfld    class System.Xml.IXmlNamespaceResolver System.Xml.XmlWellFormedWriter::predefinedNamespaces
0x3e0ec  ldarg.1
0x3e0ed  callvirt instance string System.Xml.IXmlNamespaceResolver::LookupNamespace(string prefix)
0x3e0f2  stloc.2
0x3e0f3  ldloc.2
0x3e0f4  ldarg.2
0x3e0f5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3e0fa  brtrue.s loc_3E0FF
0x3e0fc  ldc.i4.1
0x3e0fd  br.s     loc_3E100
0x3e0ff  ldc.i4.2
0x3e100  stloc.0
0x3e101  br.s     loc_3E105
0x3e103  ldc.i4.1
0x3e104  stloc.0
0x3e105  ldarg.0
0x3e106  ldarg.1
0x3e107  ldarg.2
0x3e108  ldloc.0
0x3e109  call     instance void System.Xml.XmlWellFormedWriter::AddNamespace(string prefix, string ns, valuetype NamespaceKind kind)
0x3e10e  ret
```
