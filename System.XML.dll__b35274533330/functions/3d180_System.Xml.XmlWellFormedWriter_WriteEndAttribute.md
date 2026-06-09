# System.Xml.XmlWellFormedWriter::WriteEndAttribute

- ea: `0x3d180`
- end: `0x3d4b3`
- name: `System.Xml.XmlWellFormedWriter::WriteEndAttribute`
- size: `819`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config`

## callees

- `0x211a0`
- `0x211b0`
- `0x211c0`
- `0x211d0`
- `0x3d180`
- `0x3e110`
- `0x3e4e0`
- `0x40840`
- `0x40860`
- `0x622f0`
- `0x62370`
- `0x110810`
- `0x110ab0`
- `0x110c10`
- `0x110ea0`

## string_xrefs

- `0x3d29d`: `http://www.w3.org/XML/1998/namespace`
- `0x3d405`: `http://www.w3.org/XML/1998/namespace`
- `0x3d460`: `http://www.w3.org/XML/1998/namespace`
- `0x3d239`: `http://www.w3.org/2000/xmlns/`
- `0x3d290`: `http://www.w3.org/2000/xmlns/`
- `0x3d346`: `http://www.w3.org/2000/xmlns/`
- `0x3d234`: `xmlns`
- `0x3d33b`: `xmlns`
- `0x3d27f`: `Xml_PrefixForEmptyNs`
- `0x3d3db`: `Xml_InvalidXmlSpace`
- `0x3d2bb`: `Xml_CanNotBindToReservedNamespace`

## pseudocode

```c

```

## disassembly

```asm
0x3d180  ldarg.0
0x3d181  ldc.i4.8
0x3d182  call     instance void System.Xml.XmlWellFormedWriter::AdvanceState(valuetype Token token)
0x3d187  ldarg.0
0x3d188  ldfld    valuetype SpecialAttribute System.Xml.XmlWellFormedWriter::specAttr
0x3d18d  brfalse  loc_3D49A
0x3d192  ldarg.0
0x3d193  ldfld    valuetype SpecialAttribute System.Xml.XmlWellFormedWriter::specAttr
0x3d198  stloc.1
0x3d199  ldloc.1
0x3d19a  ldc.i4.1
0x3d19b  sub
0x3d19c  switch   loc_3D1B6, loc_3D26B, loc_3D378, loc_3D42D
0x3d1b1  br       loc_3D486
0x3d1b6  ldarg.0
0x3d1b7  ldfld    class AttributeValueCache System.Xml.XmlWellFormedWriter::attrValueCache
0x3d1bc  callvirt instance string AttributeValueCache::get_StringValue()
0x3d1c1  stloc.0
0x3d1c2  ldarg.0
0x3d1c3  ldsfld   string [mscorlib]System.String::Empty
0x3d1c8  ldloc.0
0x3d1c9  call     instance bool System.Xml.XmlWellFormedWriter::PushNamespaceExplicit(string prefix, string ns)
0x3d1ce  brfalse  loc_3D25F
0x3d1d3  ldarg.0
0x3d1d4  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x3d1d9  brfalse.s loc_3D229
0x3d1db  ldarg.0
0x3d1dc  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x3d1e1  callvirt instance bool System.Xml.XmlRawWriter::get_SupportsNamespaceDeclarationInChunks()
0x3d1e6  brfalse.s loc_3D216
0x3d1e8  ldarg.0
0x3d1e9  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x3d1ee  ldsfld   string [mscorlib]System.String::Empty
0x3d1f3  callvirt instance void System.Xml.XmlRawWriter::WriteStartNamespaceDeclaration(string prefix)
0x3d1f8  ldarg.0
0x3d1f9  ldfld    class AttributeValueCache System.Xml.XmlWellFormedWriter::attrValueCache
0x3d1fe  ldarg.0
0x3d1ff  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x3d204  callvirt instance void AttributeValueCache::Replay(class System.Xml.XmlWriter writer)
0x3d209  ldarg.0
0x3d20a  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x3d20f  callvirt instance void System.Xml.XmlRawWriter::WriteEndNamespaceDeclaration()
0x3d214  br.s     loc_3D25F
0x3d216  ldarg.0
0x3d217  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x3d21c  ldsfld   string [mscorlib]System.String::Empty
0x3d221  ldloc.0
0x3d222  callvirt instance void System.Xml.XmlRawWriter::WriteNamespaceDeclaration(string prefix, string ns)
0x3d227  br.s     loc_3D25F
0x3d229  ldarg.0
0x3d22a  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x3d22f  ldsfld   string [mscorlib]System.String::Empty
0x3d234  ldstr    aXmlns// "xmlns"
0x3d239  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x3d23e  callvirt instance void System.Xml.XmlWriter::WriteStartAttribute(string prefix, string localName, string ns)
0x3d243  ldarg.0
0x3d244  ldfld    class AttributeValueCache System.Xml.XmlWellFormedWriter::attrValueCache
0x3d249  ldarg.0
0x3d24a  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x3d24f  callvirt instance void AttributeValueCache::Replay(class System.Xml.XmlWriter writer)
0x3d254  ldarg.0
0x3d255  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x3d25a  callvirt instance void System.Xml.XmlWriter::WriteEndAttribute()
0x3d25f  ldarg.0
0x3d260  ldnull
0x3d261  stfld    string System.Xml.XmlWellFormedWriter::curDeclPrefix
0x3d266  br       loc_3D486
0x3d26b  ldarg.0
0x3d26c  ldfld    class AttributeValueCache System.Xml.XmlWellFormedWriter::attrValueCache
0x3d271  callvirt instance string AttributeValueCache::get_StringValue()
0x3d276  stloc.0
0x3d277  ldloc.0
0x3d278  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3d27d  brtrue.s loc_3D28F
0x3d27f  ldstr    aXmlPrefixforem// "Xml_PrefixForEmptyNs"
0x3d284  call     string System.Xml.Res::GetString(string name)
0x3d289  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3d28e  throw
0x3d28f  ldloc.0
0x3d290  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x3d295  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3d29a  brtrue.s loc_3D2BB
0x3d29c  ldloc.0
0x3d29d  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x3d2a2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3d2a7  brfalse.s loc_3D2CB
0x3d2a9  ldarg.0
0x3d2aa  ldfld    string System.Xml.XmlWellFormedWriter::curDeclPrefix
0x3d2af  ldstr    aXml// "xml"
0x3d2b4  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3d2b9  brfalse.s loc_3D2CB
0x3d2bb  ldstr    aXmlCannotbindt// "Xml_CanNotBindToReservedNamespace"
0x3d2c0  call     string System.Xml.Res::GetString(string name)
0x3d2c5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3d2ca  throw
0x3d2cb  ldarg.0
0x3d2cc  ldarg.0
0x3d2cd  ldfld    string System.Xml.XmlWellFormedWriter::curDeclPrefix
0x3d2d2  ldloc.0
0x3d2d3  call     instance bool System.Xml.XmlWellFormedWriter::PushNamespaceExplicit(string prefix, string ns)
0x3d2d8  brfalse  loc_3D36C
0x3d2dd  ldarg.0
0x3d2de  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x3d2e3  brfalse.s loc_3D335
0x3d2e5  ldarg.0
0x3d2e6  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x3d2eb  callvirt instance bool System.Xml.XmlRawWriter::get_SupportsNamespaceDeclarationInChunks()
0x3d2f0  brfalse.s loc_3D321
0x3d2f2  ldarg.0
0x3d2f3  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x3d2f8  ldarg.0
0x3d2f9  ldfld    string System.Xml.XmlWellFormedWriter::curDeclPrefix
0x3d2fe  callvirt instance void System.Xml.XmlRawWriter::WriteStartNamespaceDeclaration(string prefix)
0x3d303  ldarg.0
0x3d304  ldfld    class AttributeValueCache System.Xml.XmlWellFormedWriter::attrValueCache
0x3d309  ldarg.0
0x3d30a  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x3d30f  callvirt instance void AttributeValueCache::Replay(class System.Xml.XmlWriter writer)
0x3d314  ldarg.0
0x3d315  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x3d31a  callvirt instance void System.Xml.XmlRawWriter::WriteEndNamespaceDeclaration()
0x3d31f  br.s     loc_3D36C
0x3d321  ldarg.0
0x3d322  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x3d327  ldarg.0
0x3d328  ldfld    string System.Xml.XmlWellFormedWriter::curDeclPrefix
0x3d32d  ldloc.0
0x3d32e  callvirt instance void System.Xml.XmlRawWriter::WriteNamespaceDeclaration(string prefix, string ns)
0x3d333  br.s     loc_3D36C
0x3d335  ldarg.0
0x3d336  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x3d33b  ldstr    aXmlns// "xmlns"
0x3d340  ldarg.0
0x3d341  ldfld    string System.Xml.XmlWellFormedWriter::curDeclPrefix
0x3d346  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x3d34b  callvirt instance void System.Xml.XmlWriter::WriteStartAttribute(string prefix, string localName, string ns)
0x3d350  ldarg.0
0x3d351  ldfld    class AttributeValueCache System.Xml.XmlWellFormedWriter::attrValueCache
0x3d356  ldarg.0
0x3d357  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x3d35c  callvirt instance void AttributeValueCache::Replay(class System.Xml.XmlWriter writer)
0x3d361  ldarg.0
0x3d362  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x3d367  callvirt instance void System.Xml.XmlWriter::WriteEndAttribute()
0x3d36c  ldarg.0
0x3d36d  ldnull
0x3d36e  stfld    string System.Xml.XmlWellFormedWriter::curDeclPrefix
0x3d373  br       loc_3D486
0x3d378  ldarg.0
0x3d379  ldfld    class AttributeValueCache System.Xml.XmlWellFormedWriter::attrValueCache
0x3d37e  callvirt instance void AttributeValueCache::Trim()
0x3d383  ldarg.0
0x3d384  ldfld    class AttributeValueCache System.Xml.XmlWellFormedWriter::attrValueCache
0x3d389  callvirt instance string AttributeValueCache::get_StringValue()
0x3d38e  stloc.0
0x3d38f  ldloc.0
0x3d390  ldstr    aDefault// "default"
0x3d395  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3d39a  brfalse.s loc_3D3B5
0x3d39c  ldarg.0
0x3d39d  ldfld    valuetype ElementScope[] System.Xml.XmlWellFormedWriter::elemScopeStack
0x3d3a2  ldarg.0
0x3d3a3  ldfld    int32 System.Xml.XmlWellFormedWriter::elemTop
0x3d3a8  ldelema  ElementScope
0x3d3ad  ldc.i4.1
0x3d3ae  stfld    valuetype System.Xml.XmlSpace ElementScope::xmlSpace
0x3d3b3  br.s     loc_3D3F5
0x3d3b5  ldloc.0
0x3d3b6  ldstr    aPreserve// "preserve"
0x3d3bb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3d3c0  brfalse.s loc_3D3DB
0x3d3c2  ldarg.0
0x3d3c3  ldfld    valuetype ElementScope[] System.Xml.XmlWellFormedWriter::elemScopeStack
0x3d3c8  ldarg.0
0x3d3c9  ldfld    int32 System.Xml.XmlWellFormedWriter::elemTop
0x3d3ce  ldelema  ElementScope
0x3d3d3  ldc.i4.2
0x3d3d4  stfld    valuetype System.Xml.XmlSpace ElementScope::xmlSpace
0x3d3d9  br.s     loc_3D3F5
0x3d3db  ldstr    aXmlInvalidxmls// "Xml_InvalidXmlSpace"
0x3d3e0  ldc.i4.1
0x3d3e1  newarr   [mscorlib]System.Object
0x3d3e6  dup
0x3d3e7  ldc.i4.0
0x3d3e8  ldloc.0
0x3d3e9  stelem.ref
0x3d3ea  call     string System.Xml.Res::GetString(string name, object[] args)
0x3d3ef  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3d3f4  throw
0x3d3f5  ldarg.0
0x3d3f6  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x3d3fb  ldstr    aXml// "xml"
0x3d400  ldstr    aSpace// "space"
0x3d405  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x3d40a  callvirt instance void System.Xml.XmlWriter::WriteStartAttribute(string prefix, string localName, string ns)
0x3d40f  ldarg.0
0x3d410  ldfld    class AttributeValueCache System.Xml.XmlWellFormedWriter::attrValueCache
0x3d415  ldarg.0
0x3d416  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x3d41b  callvirt instance void AttributeValueCache::Replay(class System.Xml.XmlWriter writer)
0x3d420  ldarg.0
0x3d421  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x3d426  callvirt instance void System.Xml.XmlWriter::WriteEndAttribute()
0x3d42b  br.s     loc_3D486
0x3d42d  ldarg.0
0x3d42e  ldfld    class AttributeValueCache System.Xml.XmlWellFormedWriter::attrValueCache
0x3d433  callvirt instance string AttributeValueCache::get_StringValue()
0x3d438  stloc.0
0x3d439  ldarg.0
0x3d43a  ldfld    valuetype ElementScope[] System.Xml.XmlWellFormedWriter::elemScopeStack
0x3d43f  ldarg.0
0x3d440  ldfld    int32 System.Xml.XmlWellFormedWriter::elemTop
0x3d445  ldelema  ElementScope
0x3d44a  ldloc.0
0x3d44b  stfld    string ElementScope::xmlLang
0x3d450  ldarg.0
0x3d451  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x3d456  ldstr    aXml// "xml"
0x3d45b  ldstr    aLang// "lang"
0x3d460  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x3d465  callvirt instance void System.Xml.XmlWriter::WriteStartAttribute(string prefix, string localName, string ns)
0x3d46a  ldarg.0
0x3d46b  ldfld    class AttributeValueCache System.Xml.XmlWellFormedWriter::attrValueCache
0x3d470  ldarg.0
0x3d471  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x3d476  callvirt instance void AttributeValueCache::Replay(class System.Xml.XmlWriter writer)
0x3d47b  ldarg.0
0x3d47c  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x3d481  callvirt instance void System.Xml.XmlWriter::WriteEndAttribute()
0x3d486  ldarg.0
0x3d487  ldc.i4.0
0x3d488  stfld    valuetype SpecialAttribute System.Xml.XmlWellFormedWriter::specAttr
0x3d48d  ldarg.0
0x3d48e  ldfld    class AttributeValueCache System.Xml.XmlWellFormedWriter::attrValueCache
0x3d493  callvirt instance void AttributeValueCache::Clear()
0x3d498  br.s     loc_3D4A5
0x3d49a  ldarg.0
0x3d49b  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x3d4a0  callvirt instance void System.Xml.XmlWriter::WriteEndAttribute()
0x3d4a5  leave.s  loc_3D4B2
0x3d4a7  pop
0x3d4a8  ldarg.0
0x3d4a9  ldc.i4.s 0x10
0x3d4ab  stfld    valuetype State System.Xml.XmlWellFormedWriter::currentState
0x3d4b0  rethrow
0x3d4b2  ret
```
