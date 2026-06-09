# System.Xml.Serialization.SoapSchemaImporter::ImportGroupMembers

- ea: `0x716e0`
- end: `0x71803`
- name: `System.Xml.Serialization.SoapSchemaImporter::ImportGroupMembers`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x71690`

## callees

- `0x13310`
- `0x13320`
- `0x622f0`
- `0x716e0`
- `0x71bf0`
- `0x85600`
- `0xd36a0`
- `0xd3eb0`
- `0xd4530`

## string_xrefs

- `0x716ef`: `XmlSoapUnsupportedGroupRef`
- `0x71731`: `XmlSoapUnsupportedGroupRepeat`
- `0x7177d`: `XmlSoapUnsupportedGroupNested`
- `0x717c5`: `XmlSoapUnsupportedGroupAny`

## pseudocode

```c

```

## disassembly

```asm
0x716e0  ldarg.1
0x716e1  call     class System.Xml.XmlQualifiedName System.Xml.Serialization.XmlSchemas::GetParentName(class System.Xml.Schema.XmlSchemaObject item)
0x716e6  stloc.0
0x716e7  ldarg.1
0x716e8  isinst   System.Xml.Schema.XmlSchemaGroupRef
0x716ed  brfalse.s loc_71717
0x716ef  ldstr    aXmlsoapunsuppo// "XmlSoapUnsupportedGroupRef"
0x716f4  ldc.i4.2
0x716f5  newarr   [mscorlib]System.Object
0x716fa  dup
0x716fb  ldc.i4.0
0x716fc  ldloc.0
0x716fd  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x71702  stelem.ref
0x71703  dup
0x71704  ldc.i4.1
0x71705  ldloc.0
0x71706  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x7170b  stelem.ref
0x7170c  call     string System.Xml.Res::GetString(string name, object[] args)
0x71711  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x71716  throw
0x71717  ldarg.1
0x71718  isinst   System.Xml.Schema.XmlSchemaGroupBase
0x7171d  brfalse  loc_71802
0x71722  ldarg.1
0x71723  castclass System.Xml.Schema.XmlSchemaGroupBase
0x71728  stloc.1
0x71729  ldloc.1
0x7172a  callvirt instance bool System.Xml.Schema.XmlSchemaParticle::get_IsMultipleOccurrence()
0x7172f  brfalse.s loc_71759
0x71731  ldstr    aXmlsoapunsuppo_0// "XmlSoapUnsupportedGroupRepeat"
0x71736  ldc.i4.2
0x71737  newarr   [mscorlib]System.Object
0x7173c  dup
0x7173d  ldc.i4.0
0x7173e  ldloc.0
0x7173f  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x71744  stelem.ref
0x71745  dup
0x71746  ldc.i4.1
0x71747  ldloc.0
0x71748  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x7174d  stelem.ref
0x7174e  call     string System.Xml.Res::GetString(string name, object[] args)
0x71753  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x71758  throw
0x71759  ldc.i4.0
0x7175a  stloc.2
0x7175b  br       loc_717F1
0x71760  ldloc.1
0x71761  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x71766  ldloc.2
0x71767  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0x7176c  stloc.3
0x7176d  ldloc.3
0x7176e  isinst   System.Xml.Schema.XmlSchemaGroupBase
0x71773  brtrue.s loc_7177D
0x71775  ldloc.3
0x71776  isinst   System.Xml.Schema.XmlSchemaGroupRef
0x7177b  brfalse.s loc_717A5
0x7177d  ldstr    aXmlsoapunsuppo_1// "XmlSoapUnsupportedGroupNested"
0x71782  ldc.i4.2
0x71783  newarr   [mscorlib]System.Object
0x71788  dup
0x71789  ldc.i4.0
0x7178a  ldloc.0
0x7178b  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x71790  stelem.ref
0x71791  dup
0x71792  ldc.i4.1
0x71793  ldloc.0
0x71794  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x71799  stelem.ref
0x7179a  call     string System.Xml.Res::GetString(string name, object[] args)
0x7179f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x717a4  throw
0x717a5  ldloc.3
0x717a6  isinst   System.Xml.Schema.XmlSchemaElement
0x717ab  brfalse.s loc_717BD
0x717ad  ldarg.0
0x717ae  ldloc.3
0x717af  castclass System.Xml.Schema.XmlSchemaElement
0x717b4  ldarg.2
0x717b5  ldarg.3
0x717b6  call     instance void System.Xml.Serialization.SoapSchemaImporter::ImportElementMember(class System.Xml.Schema.XmlSchemaElement element, class System.Xml.Serialization.CodeIdentifiers members, string ns)
0x717bb  br.s     loc_717ED
0x717bd  ldloc.3
0x717be  isinst   System.Xml.Schema.XmlSchemaAny
0x717c3  brfalse.s loc_717ED
0x717c5  ldstr    aXmlsoapunsuppo_2// "XmlSoapUnsupportedGroupAny"
0x717ca  ldc.i4.2
0x717cb  newarr   [mscorlib]System.Object
0x717d0  dup
0x717d1  ldc.i4.0
0x717d2  ldloc.0
0x717d3  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x717d8  stelem.ref
0x717d9  dup
0x717da  ldc.i4.1
0x717db  ldloc.0
0x717dc  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x717e1  stelem.ref
0x717e2  call     string System.Xml.Res::GetString(string name, object[] args)
0x717e7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x717ec  throw
0x717ed  ldloc.2
0x717ee  ldc.i4.1
0x717ef  add
0x717f0  stloc.2
0x717f1  ldloc.2
0x717f2  ldloc.1
0x717f3  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x717f8  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x717fd  blt      loc_71760
0x71802  ret
```
