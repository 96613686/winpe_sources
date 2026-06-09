# System.Xml.Serialization.SoapSchemaImporter::ImportTypeMembers

- ea: `0x714e0`
- end: `0x71684`
- name: `System.Xml.Serialization.SoapSchemaImporter::ImportTypeMembers`
- size: `420`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x70dd0`
- `0x71350`

## callees

- `0x13310`
- `0x622f0`
- `0x65b50`
- `0x714e0`
- `0x71690`
- `0xd09c0`
- `0xd1590`
- `0xd1650`
- `0xd1990`
- `0xd19b0`
- `0xd19d0`
- `0xd19f0`
- `0xd2160`
- `0xd3eb0`
- `0xd6af0`
- `0xd6b30`

## string_xrefs

- `0x714e8`: `XmlInvalidAnyAttributeUse`
- `0x71533`: `XmlSoapInvalidAttributeUse`
- `0x71578`: `XmlSoapInvalidAttributeUse`

## pseudocode

```c

```

## disassembly

```asm
0x714e0  ldarg.1
0x714e1  callvirt instance class System.Xml.Schema.XmlSchemaAnyAttribute System.Xml.Schema.XmlSchemaComplexType::get_AnyAttribute()
0x714e6  brfalse.s loc_71515
0x714e8  ldstr    aXmlinvalidanya// "XmlInvalidAnyAttributeUse"
0x714ed  ldc.i4.2
0x714ee  newarr   [mscorlib]System.Object
0x714f3  dup
0x714f4  ldc.i4.0
0x714f5  ldarg.1
0x714f6  callvirt instance string System.Xml.Schema.XmlSchemaType::get_Name()
0x714fb  stelem.ref
0x714fc  dup
0x714fd  ldc.i4.1
0x714fe  ldarg.1
0x714ff  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0x71504  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x71509  stelem.ref
0x7150a  call     string System.Xml.Res::GetString(string name, object[] args)
0x7150f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x71514  throw
0x71515  ldarg.1
0x71516  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaComplexType::get_Attributes()
0x7151b  stloc.0
0x7151c  ldc.i4.0
0x7151d  stloc.1
0x7151e  br       loc_715A9
0x71523  ldloc.0
0x71524  ldloc.1
0x71525  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0x7152a  stloc.2
0x7152b  ldloc.2
0x7152c  isinst   System.Xml.Schema.XmlSchemaAttributeGroup
0x71531  brfalse.s loc_71560
0x71533  ldstr    aXmlsoapinvalid// "XmlSoapInvalidAttributeUse"
0x71538  ldc.i4.2
0x71539  newarr   [mscorlib]System.Object
0x7153e  dup
0x7153f  ldc.i4.0
0x71540  ldarg.1
0x71541  callvirt instance string System.Xml.Schema.XmlSchemaType::get_Name()
0x71546  stelem.ref
0x71547  dup
0x71548  ldc.i4.1
0x71549  ldarg.1
0x7154a  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0x7154f  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x71554  stelem.ref
0x71555  call     string System.Xml.Res::GetString(string name, object[] args)
0x7155a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7155f  throw
0x71560  ldloc.2
0x71561  isinst   System.Xml.Schema.XmlSchemaAttribute
0x71566  brfalse.s loc_715A5
0x71568  ldloc.2
0x71569  castclass System.Xml.Schema.XmlSchemaAttribute
0x7156e  stloc.3
0x7156f  ldloc.3
0x71570  callvirt instance valuetype System.Xml.Schema.XmlSchemaUse System.Xml.Schema.XmlSchemaAttribute::get_Use()
0x71575  ldc.i4.2
0x71576  beq.s    loc_715A5
0x71578  ldstr    aXmlsoapinvalid// "XmlSoapInvalidAttributeUse"
0x7157d  ldc.i4.2
0x7157e  newarr   [mscorlib]System.Object
0x71583  dup
0x71584  ldc.i4.0
0x71585  ldarg.1
0x71586  callvirt instance string System.Xml.Schema.XmlSchemaType::get_Name()
0x7158b  stelem.ref
0x7158c  dup
0x7158d  ldc.i4.1
0x7158e  ldarg.1
0x7158f  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0x71594  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x71599  stelem.ref
0x7159a  call     string System.Xml.Res::GetString(string name, object[] args)
0x7159f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x715a4  throw
0x715a5  ldloc.1
0x715a6  ldc.i4.1
0x715a7  add
0x715a8  stloc.1
0x715a9  ldloc.1
0x715aa  ldloc.0
0x715ab  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x715b0  blt      loc_71523
0x715b5  ldarg.1
0x715b6  callvirt instance class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.XmlSchemaComplexType::get_Particle()
0x715bb  brfalse.s loc_715D0
0x715bd  ldarg.0
0x715be  ldarg.1
0x715bf  callvirt instance class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.XmlSchemaComplexType::get_Particle()
0x715c4  ldarg.3
0x715c5  ldarg.2
0x715c6  call     instance void System.Xml.Serialization.SoapSchemaImporter::ImportGroup(class System.Xml.Schema.XmlSchemaParticle group, class System.Xml.Serialization.CodeIdentifiers members, string ns)
0x715cb  br       loc_7166E
0x715d0  ldarg.1
0x715d1  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x715d6  brfalse  loc_7166E
0x715db  ldarg.1
0x715dc  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x715e1  isinst   System.Xml.Schema.XmlSchemaComplexContent
0x715e6  brfalse  loc_7166E
0x715eb  ldarg.1
0x715ec  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x715f1  castclass System.Xml.Schema.XmlSchemaComplexContent
0x715f6  stloc.s  4
0x715f8  ldloc.s  4
0x715fa  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x715ff  isinst   System.Xml.Schema.XmlSchemaComplexContentExtension
0x71604  brfalse.s loc_71634
0x71606  ldloc.s  4
0x71608  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x7160d  castclass System.Xml.Schema.XmlSchemaComplexContentExtension
0x71612  callvirt instance class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.XmlSchemaComplexContentExtension::get_Particle()
0x71617  brfalse.s loc_7166E
0x71619  ldarg.0
0x7161a  ldloc.s  4
0x7161c  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x71621  castclass System.Xml.Schema.XmlSchemaComplexContentExtension
0x71626  callvirt instance class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.XmlSchemaComplexContentExtension::get_Particle()
0x7162b  ldarg.3
0x7162c  ldarg.2
0x7162d  call     instance void System.Xml.Serialization.SoapSchemaImporter::ImportGroup(class System.Xml.Schema.XmlSchemaParticle group, class System.Xml.Serialization.CodeIdentifiers members, string ns)
0x71632  br.s     loc_7166E
0x71634  ldloc.s  4
0x71636  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x7163b  isinst   System.Xml.Schema.XmlSchemaComplexContentRestriction
0x71640  brfalse.s loc_7166E
0x71642  ldloc.s  4
0x71644  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x71649  castclass System.Xml.Schema.XmlSchemaComplexContentRestriction
0x7164e  callvirt instance class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.XmlSchemaComplexContentRestriction::get_Particle()
0x71653  brfalse.s loc_7166E
0x71655  ldarg.0
0x71656  ldloc.s  4
0x71658  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x7165d  castclass System.Xml.Schema.XmlSchemaComplexContentRestriction
0x71662  callvirt instance class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.XmlSchemaComplexContentRestriction::get_Particle()
0x71667  ldarg.3
0x71668  ldarg.2
0x71669  call     instance void System.Xml.Serialization.SoapSchemaImporter::ImportGroup(class System.Xml.Schema.XmlSchemaParticle group, class System.Xml.Serialization.CodeIdentifiers members, string ns)
0x7166e  ldarg.3
0x7166f  ldtoken  System.Xml.Serialization.MemberMapping
0x71674  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x71679  callvirt instance object System.Xml.Serialization.CodeIdentifiers::ToArray(class [mscorlib]System.Type type)
0x7167e  castclass class System.Xml.Serialization.MemberMapping[]
0x71683  ret
```
