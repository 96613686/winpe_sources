# System.Xml.Serialization.XmlSchemaExporter::ExportTypeMembers

- ea: `0x808d0`
- end: `0x80b8e`
- name: `System.Xml.Serialization.XmlSchemaExporter::ExportTypeMembers`
- size: `702`
- prototype: ``
- caller_count: `2`
- callee_count: `34`
- tags: `registry_config`

## callers

- `0x7faf0`
- `0x80620`

## callees

- `0x622f0`
- `0x68600`
- `0x68690`
- `0x686a0`
- `0x68b30`
- `0x68c50`
- `0x68c90`
- `0x68cd0`
- `0x69620`
- `0x69640`
- `0x69660`
- `0x696f0`
- `0x69750`
- `0x69ae0`
- `0x69b00`
- `0x72b80`
- `0x72dd0`
- `0x7fb70`
- `0x7fce0`
- `0x7fd70`
- `0x808d0`
- `0xd15a0`
- `0xd1660`
- `0xd1990`
- `0xd19a0`
- `0xd19c0`
- `0xd2160`
- `0xd2170`
- `0xd36a0`
- `0xd46e0`
- `0xd64f0`
- `0xd6520`
- `0xd6580`
- `0xd6bd0`

## string_xrefs

- `0x80a0e`: `XmlInvalidContent`
- `0x808fc`: `XmlIllegalMultipleText`
- `0x80a91`: `XmlAnonymousBaseType`

## pseudocode

```c

```

## disassembly

```asm
0x808d0  newobj   instance void System.Xml.Schema.XmlSchemaSequence::.ctor()
0x808d5  stloc.0
0x808d6  ldnull
0x808d7  stloc.1
0x808d8  ldc.i4.0
0x808d9  stloc.3
0x808da  br       loc_80995
0x808df  ldarg.2
0x808e0  ldloc.3
0x808e1  ldelem.ref
0x808e2  stloc.s  4
0x808e4  ldloc.s  4
0x808e6  callvirt instance bool System.Xml.Serialization.AccessorMapping::get_Ignore()
0x808eb  brtrue   loc_80991
0x808f0  ldloc.s  4
0x808f2  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x808f7  brfalse.s loc_80923
0x808f9  ldloc.1
0x808fa  brfalse.s loc_80916
0x808fc  ldstr    aXmlillegalmult// "XmlIllegalMultipleText"
0x80901  ldc.i4.1
0x80902  newarr   [mscorlib]System.Object
0x80907  dup
0x80908  ldc.i4.0
0x80909  ldarg.3
0x8090a  stelem.ref
0x8090b  call     string System.Xml.Res::GetString(string name, object[] args)
0x80910  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x80915  throw
0x80916  ldloc.s  4
0x80918  callvirt instance class System.Xml.Serialization.TextAccessor System.Xml.Serialization.AccessorMapping::get_Text()
0x8091d  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x80922  stloc.1
0x80923  ldloc.s  4
0x80925  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.AccessorMapping::get_Elements()
0x8092a  ldlen
0x8092b  brfalse.s loc_80991
0x8092d  ldloc.s  4
0x8092f  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x80934  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsArrayLike()
0x80939  brfalse.s loc_80965
0x8093b  ldloc.s  4
0x8093d  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.AccessorMapping::get_Elements()
0x80942  ldlen
0x80943  conv.i4
0x80944  ldc.i4.1
0x80945  bne.un.s loc_80962
0x80947  ldloc.s  4
0x80949  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.AccessorMapping::get_Elements()
0x8094e  ldc.i4.0
0x8094f  ldelem.ref
0x80950  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x80955  isinst   System.Xml.Serialization.ArrayMapping
0x8095a  ldnull
0x8095b  cgt.un
0x8095d  ldc.i4.0
0x8095e  ceq
0x80960  br.s     loc_80966
0x80962  ldc.i4.1
0x80963  br.s     loc_80966
0x80965  ldc.i4.0
0x80966  stloc.s  5
0x80968  ldloc.s  4
0x8096a  callvirt instance valuetype System.Xml.Serialization.SpecifiedAccessor System.Xml.Serialization.MemberMapping::get_CheckSpecified()
0x8096f  brtrue.s loc_8097A
0x80971  ldloc.s  4
0x80973  callvirt instance bool System.Xml.Serialization.MemberMapping::get_CheckShouldPersist()
0x80978  br.s     loc_8097B
0x8097a  ldc.i4.1
0x8097b  stloc.s  6
0x8097d  ldarg.0
0x8097e  ldloc.0
0x8097f  ldloc.s  4
0x80981  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.AccessorMapping::get_Elements()
0x80986  ldloc.s  5
0x80988  ldloc.s  6
0x8098a  ldarg.s  4
0x8098c  call     instance void System.Xml.Serialization.XmlSchemaExporter::ExportElementAccessors(class System.Xml.Schema.XmlSchemaGroupBase group, class System.Xml.Serialization.ElementAccessor[] accessors, bool repeats, bool valueTypeOptional, string ns)
0x80991  ldloc.3
0x80992  ldc.i4.1
0x80993  add
0x80994  stloc.3
0x80995  ldloc.3
0x80996  ldarg.2
0x80997  ldlen
0x80998  conv.i4
0x80999  blt      loc_808DF
0x8099e  ldloc.0
0x8099f  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x809a4  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x809a9  ldc.i4.0
0x809aa  ble      loc_80A43
0x809af  ldarg.1
0x809b0  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x809b5  brfalse  loc_80A3C
0x809ba  ldarg.1
0x809bb  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x809c0  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x809c5  isinst   System.Xml.Schema.XmlSchemaComplexContentRestriction
0x809ca  brfalse.s loc_809E4
0x809cc  ldarg.1
0x809cd  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x809d2  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x809d7  castclass System.Xml.Schema.XmlSchemaComplexContentRestriction
0x809dc  ldloc.0
0x809dd  callvirt instance void System.Xml.Schema.XmlSchemaComplexContentRestriction::set_Particle(class System.Xml.Schema.XmlSchemaParticle value)
0x809e2  br.s     loc_80A43
0x809e4  ldarg.1
0x809e5  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x809ea  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x809ef  isinst   System.Xml.Schema.XmlSchemaComplexContentExtension
0x809f4  brfalse.s loc_80A0E
0x809f6  ldarg.1
0x809f7  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x809fc  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x80a01  castclass System.Xml.Schema.XmlSchemaComplexContentExtension
0x80a06  ldloc.0
0x80a07  callvirt instance void System.Xml.Schema.XmlSchemaComplexContentExtension::set_Particle(class System.Xml.Schema.XmlSchemaParticle value)
0x80a0c  br.s     loc_80A43
0x80a0e  ldstr    aXmlinvalidcont// "XmlInvalidContent"
0x80a13  ldc.i4.1
0x80a14  newarr   [mscorlib]System.Object
0x80a19  dup
0x80a1a  ldc.i4.0
0x80a1b  ldarg.1
0x80a1c  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x80a21  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x80a26  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x80a2b  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x80a30  stelem.ref
0x80a31  call     string System.Xml.Res::GetString(string name, object[] args)
0x80a36  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x80a3b  throw
0x80a3c  ldarg.1
0x80a3d  ldloc.0
0x80a3e  callvirt instance void System.Xml.Schema.XmlSchemaComplexType::set_Particle(class System.Xml.Schema.XmlSchemaParticle value)
0x80a43  ldloc.1
0x80a44  brfalse  loc_80B0D
0x80a49  ldarg.s  5
0x80a4b  brfalse  loc_80B06
0x80a50  ldloc.1
0x80a51  isinst   System.Xml.Serialization.PrimitiveMapping
0x80a56  brfalse  loc_80B0D
0x80a5b  ldloc.0
0x80a5c  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x80a61  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x80a66  brtrue   loc_80B0D
0x80a6b  ldloc.1
0x80a6c  castclass System.Xml.Serialization.PrimitiveMapping
0x80a71  stloc.s  7
0x80a73  ldloc.s  7
0x80a75  callvirt instance bool System.Xml.Serialization.TypeMapping::get_IsList()
0x80a7a  brfalse.s loc_80A88
0x80a7c  ldarg.1
0x80a7d  ldc.i4.1
0x80a7e  callvirt instance void System.Xml.Schema.XmlSchemaType::set_IsMixed(bool value)
0x80a83  br       loc_80B0D
0x80a88  ldloc.s  7
0x80a8a  callvirt instance bool System.Xml.Serialization.TypeMapping::get_IsAnonymousType()
0x80a8f  brfalse.s loc_80AD4
0x80a91  ldstr    aXmlanonymousba// "XmlAnonymousBaseType"
0x80a96  ldc.i4.4
0x80a97  newarr   [mscorlib]System.Object
0x80a9c  dup
0x80a9d  ldc.i4.0
0x80a9e  ldloc.1
0x80a9f  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x80aa4  callvirt instance string System.Xml.Serialization.TypeDesc::get_Name()
0x80aa9  stelem.ref
0x80aaa  dup
0x80aab  ldc.i4.1
0x80aac  ldloc.s  7
0x80aae  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x80ab3  callvirt instance string System.Xml.Serialization.TypeDesc::get_Name()
0x80ab8  stelem.ref
0x80ab9  dup
0x80aba  ldc.i4.2
0x80abb  ldstr    aAnonymoustype// "AnonymousType"
0x80ac0  stelem.ref
0x80ac1  dup
0x80ac2  ldc.i4.3
0x80ac3  ldstr    aFalse// "false"
0x80ac8  stelem.ref
0x80ac9  call     string System.Xml.Res::GetString(string name, object[] args)
0x80ace  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x80ad3  throw
0x80ad4  newobj   instance void System.Xml.Schema.XmlSchemaSimpleContent::.ctor()
0x80ad9  stloc.s  8
0x80adb  newobj   instance void System.Xml.Schema.XmlSchemaSimpleContentExtension::.ctor()
0x80ae0  stloc.s  9
0x80ae2  ldloc.s  8
0x80ae4  ldloc.s  9
0x80ae6  callvirt instance void System.Xml.Schema.XmlSchemaContentModel::set_Content(class System.Xml.Schema.XmlSchemaContent value)
0x80aeb  ldarg.1
0x80aec  ldloc.s  8
0x80aee  callvirt instance void System.Xml.Schema.XmlSchemaComplexType::set_ContentModel(class System.Xml.Schema.XmlSchemaContentModel value)
0x80af3  ldloc.s  9
0x80af5  ldarg.0
0x80af6  ldloc.s  7
0x80af8  ldarg.s  4
0x80afa  call     instance class System.Xml.XmlQualifiedName System.Xml.Serialization.XmlSchemaExporter::ExportPrimitiveMapping(class System.Xml.Serialization.PrimitiveMapping mapping, string ns)
0x80aff  callvirt instance void System.Xml.Schema.XmlSchemaSimpleContentExtension::set_BaseTypeName(class System.Xml.XmlQualifiedName value)
0x80b04  br.s     loc_80B0D
0x80b06  ldarg.1
0x80b07  ldc.i4.1
0x80b08  callvirt instance void System.Xml.Schema.XmlSchemaType::set_IsMixed(bool value)
0x80b0d  ldc.i4.0
0x80b0e  stloc.2
0x80b0f  ldc.i4.0
0x80b10  stloc.s  0xA
0x80b12  br.s     loc_80B64
0x80b14  ldarg.2
0x80b15  ldloc.s  0xA
0x80b17  ldelem.ref
0x80b18  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x80b1d  stloc.s  0xB
0x80b1f  ldloc.s  0xB
0x80b21  brfalse.s loc_80B5E
0x80b23  ldarg.0
0x80b24  ldarg.1
0x80b25  ldarg.2
0x80b26  ldloc.s  0xA
0x80b28  ldelem.ref
0x80b29  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x80b2e  ldarg.2
0x80b2f  ldloc.s  0xA
0x80b31  ldelem.ref
0x80b32  callvirt instance valuetype System.Xml.Serialization.SpecifiedAccessor System.Xml.Serialization.MemberMapping::get_CheckSpecified()
0x80b37  brtrue.s loc_80B44
0x80b39  ldarg.2
0x80b3a  ldloc.s  0xA
0x80b3c  ldelem.ref
0x80b3d  callvirt instance bool System.Xml.Serialization.MemberMapping::get_CheckShouldPersist()
0x80b42  br.s     loc_80B45
0x80b44  ldc.i4.1
0x80b45  ldarg.s  4
0x80b47  call     instance void System.Xml.Serialization.XmlSchemaExporter::ExportAttributeAccessor(class System.Xml.Schema.XmlSchemaComplexType type, class System.Xml.Serialization.AttributeAccessor accessor, bool valueTypeOptional, string ns)
0x80b4c  ldarg.2
0x80b4d  ldloc.s  0xA
0x80b4f  ldelem.ref
0x80b50  callvirt instance class System.Xml.Serialization.AttributeAccessor System.Xml.Serialization.AccessorMapping::get_Attribute()
0x80b55  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0x80b5a  brfalse.s loc_80B5E
0x80b5c  ldc.i4.1
0x80b5d  stloc.2
0x80b5e  ldloc.s  0xA
0x80b60  ldc.i4.1
0x80b61  add
0x80b62  stloc.s  0xA
0x80b64  ldloc.s  0xA
0x80b66  ldarg.2
0x80b67  ldlen
0x80b68  conv.i4
0x80b69  blt.s    loc_80B14
0x80b6b  ldarg.s  6
0x80b6d  brfalse.s loc_80B8D
0x80b6f  ldloc.2
0x80b70  brtrue.s loc_80B8D
0x80b72  newobj   instance void System.Xml.Serialization.AttributeAccessor::.ctor()
0x80b77  stloc.s  0xC
0x80b79  ldloc.s  0xC
0x80b7b  ldc.i4.1
0x80b7c  callvirt instance void System.Xml.Serialization.Accessor::set_Any(bool value)
0x80b81  ldarg.0
0x80b82  ldarg.1
0x80b83  ldloc.s  0xC
0x80b85  ldc.i4.0
0x80b86  ldarg.s  4
0x80b88  call     instance void System.Xml.Serialization.XmlSchemaExporter::ExportAttributeAccessor(class System.Xml.Schema.XmlSchemaComplexType type, class System.Xml.Serialization.AttributeAccessor accessor, bool valueTypeOptional, string ns)
0x80b8d  ret
```
