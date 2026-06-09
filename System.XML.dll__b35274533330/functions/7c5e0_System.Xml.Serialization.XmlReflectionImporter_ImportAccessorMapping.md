# System.Xml.Serialization.XmlReflectionImporter::ImportAccessorMapping

- ea: `0x7c5e0`
- end: `0x7e073`
- name: `System.Xml.Serialization.XmlReflectionImporter::ImportAccessorMapping`
- size: `6803`
- prototype: ``
- caller_count: `2`
- callee_count: `133`
- tags: `registry_config`

## callers

- `0x7bf60`
- `0x7c1e0`

## callees

- `0xf5b0`
- `0x622f0`
- `0x62370`
- `0x68600`
- `0x68610`
- `0x68630`
- `0x68660`
- `0x68680`
- `0x68690`
- `0x686a0`
- `0x686b0`
- `0x686c0`
- `0x686d0`
- `0x686e0`
- `0x686f0`
- `0x68700`
- `0x68790`
- `0x688b0`
- `0x688c0`
- `0x68970`
- `0x689a0`
- `0x689b0`
- `0x689c0`
- `0x689e0`
- `0x689f0`
- `0x68a10`
- `0x68a30`
- `0x68a70`
- `0x68a80`
- `0x68b30`
- `0x68c10`
- `0x68c50`
- `0x68cf0`
- `0x68ec0`
- `0x68f00`
- `0x68f30`
- `0x69620`
- `0x69630`
- `0x69650`
- `0x69660`
- `0x69670`
- `0x69700`
- `0x69710`
- `0x69720`
- `0x69730`
- `0x69740`
- `0x69760`
- `0x69b20`
- `0x69c10`
- `0x6a6b0`

## string_xrefs

- `0x7cc6e`: `XmlInvalidNotNullable`
- `0x7d605`: `XmlInvalidNotNullable`
- `0x7d9a3`: `XmlInvalidNotNullable`
- `0x7d2b1`: `XmlAttribute`
- `0x7c772`: `XmlIllegalAttributesArrayAttribute`
- `0x7c7cb`: `XmlIllegalAttrOrTextInterface`
- `0x7d7cf`: `XmlIllegalAttrOrTextInterface`
- `0x7c80b`: `XmlIllegalAttrOrText`
- `0x7d80a`: `XmlIllegalAttrOrText`
- `0x7ca1f`: `XmlIllegalElementsArrayAttribute`
- `0x7cad1`: `XmlIllegalArrayTextAttribute`
- `0x7cc8f`: `XmlElement`
- `0x7d517`: `XmlElement`
- `0x7d626`: `XmlElement`
- `0x7d9c4`: `XmlElement`
- `0x7cd3d`: `XmlSequenceMatch`
- `0x7cfe9`: `XmlSequenceMatch`
- `0x7d6d8`: `XmlSequenceMatch`
- `0x7da72`: `XmlSequenceMatch`
- `0x7dd00`: `XmlSequenceMatch`
- `0x7cdf1`: `XmlIllegalAnyElement`
- `0x7d244`: `XmlIllegalAnyElement`
- `0x7db26`: `XmlIllegalAnyElement`
- `0x7ce7d`: `XmlAnyElementDuplicate`
- `0x7dbb2`: `XmlAnyElementDuplicate`
- `0x7d03c`: `XmlIllegalArrayArrayAttribute`
- `0x7d209`: `XmlIllegalAttribute`
- `0x7d281`: `XmlIllegalAttribute`
- `0x7d2a4`: `XmlIllegalType`
- `0x7d443`: `XmlIllegalType`
- `0x7d50a`: `XmlIllegalType`
- `0x7d450`: `XmlText`
- `0x7d73f`: `XmlSoleXmlnsAttribute`
- `0x7d762`: `XmlXmlnsInvalidType`
- `0x7ddb0`: `XmlRpcLitArrayElement`
- `0x7ddde`: `XmlRpcLitXmlns`
- `0x7df97`: `XmlChoiceMissingAnyValue`
- `0x7e000`: `XmlChoiceMissingValue`

## pseudocode

```c

```

## disassembly

```asm
0x7c5e0  ldc.i4.1
0x7c5e1  stloc.0
0x7c5e2  ldarg.0
0x7c5e3  ldfld    int32 System.Xml.Serialization.XmlReflectionImporter::arrayNestingLevel
0x7c5e8  stloc.1
0x7c5e9  ldc.i4.m1
0x7c5ea  stloc.2
0x7c5eb  ldarg.0
0x7c5ec  ldfld    class System.Xml.Serialization.XmlArrayItemAttributes System.Xml.Serialization.XmlReflectionImporter::savedArrayItemAttributes
0x7c5f1  stloc.3
0x7c5f2  ldarg.0
0x7c5f3  ldfld    string System.Xml.Serialization.XmlReflectionImporter::savedArrayNamespace
0x7c5f8  stloc.s  4
0x7c5fa  ldarg.0
0x7c5fb  ldc.i4.0
0x7c5fc  stfld    int32 System.Xml.Serialization.XmlReflectionImporter::arrayNestingLevel
0x7c601  ldarg.0
0x7c602  ldnull
0x7c603  stfld    class System.Xml.Serialization.XmlArrayItemAttributes System.Xml.Serialization.XmlReflectionImporter::savedArrayItemAttributes
0x7c608  ldarg.0
0x7c609  ldnull
0x7c60a  stfld    string System.Xml.Serialization.XmlReflectionImporter::savedArrayNamespace
0x7c60f  ldarg.2
0x7c610  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.FieldModel::get_FieldType()
0x7c615  stloc.s  5
0x7c617  ldarg.2
0x7c618  callvirt instance string System.Xml.Serialization.FieldModel::get_Name()
0x7c61d  stloc.s  6
0x7c61f  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x7c624  stloc.s  7
0x7c626  newobj   instance void System.Xml.Serialization.NameTable::.ctor()
0x7c62b  stloc.s  8
0x7c62d  ldarg.1
0x7c62e  ldarg.0
0x7c62f  ldfld    class System.Xml.Serialization.TypeScope System.Xml.Serialization.XmlReflectionImporter::typeScope
0x7c634  ldloc.s  5
0x7c636  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeScope::GetTypeDesc(class [mscorlib]System.Type type)
0x7c63b  callvirt instance void System.Xml.Serialization.AccessorMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x7c640  ldarg.3
0x7c641  callvirt instance valuetype System.Xml.Serialization.XmlAttributeFlags System.Xml.Serialization.XmlAttributes::get_XmlFlags()
0x7c646  stloc.s  9
0x7c648  ldarg.1
0x7c649  ldarg.3
0x7c64a  callvirt instance bool System.Xml.Serialization.XmlAttributes::get_XmlIgnore()
0x7c64f  callvirt instance void System.Xml.Serialization.AccessorMapping::set_Ignore(bool value)
0x7c654  ldarg.s  6
0x7c656  brfalse.s loc_7C663
0x7c658  ldarg.0
0x7c659  ldarg.3
0x7c65a  ldloc.s  6
0x7c65c  call     instance void System.Xml.Serialization.XmlReflectionImporter::CheckTopLevelAttributes(class System.Xml.Serialization.XmlAttributes a, string accessorName)
0x7c661  br.s     loc_7C66E
0x7c663  ldarg.0
0x7c664  ldarg.3
0x7c665  ldloc.s  5
0x7c667  ldloc.s  6
0x7c669  call     instance void System.Xml.Serialization.XmlReflectionImporter::CheckAmbiguousChoice(class System.Xml.Serialization.XmlAttributes a, class [mscorlib]System.Type accessorType, string accessorName)
0x7c66e  ldc.i4   0x514
0x7c673  stloc.s  0xA
0x7c675  ldc.i4   0x220
0x7c67a  stloc.s  0xB
0x7c67c  ldc.i4.s 0xA
0x7c67e  stloc.s  0xC
0x7c680  ldloc.s  9
0x7c682  ldloc.s  0xC
0x7c684  and
0x7c685  brfalse.s loc_7C6AD
0x7c687  ldloc.s  5
0x7c689  ldtoken  unsigned int8[]
0x7c68e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7c693  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7c698  brfalse.s loc_7C6AD
0x7c69a  ldarg.1
0x7c69b  ldarg.0
0x7c69c  ldfld    class System.Xml.Serialization.TypeScope System.Xml.Serialization.XmlReflectionImporter::typeScope
0x7c6a1  ldloc.s  5
0x7c6a3  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeScope::GetArrayTypeDesc(class [mscorlib]System.Type type)
0x7c6a8  callvirt instance void System.Xml.Serialization.AccessorMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x7c6ad  ldarg.3
0x7c6ae  callvirt instance class System.Xml.Serialization.XmlChoiceIdentifierAttribute System.Xml.Serialization.XmlAttributes::get_XmlChoiceIdentifier()
0x7c6b3  brfalse.s loc_7C72B
0x7c6b5  ldarg.1
0x7c6b6  newobj   instance void System.Xml.Serialization.ChoiceIdentifierAccessor::.ctor()
0x7c6bb  callvirt instance void System.Xml.Serialization.AccessorMapping::set_ChoiceIdentifier(class System.Xml.Serialization.ChoiceIdentifierAccessor value)
0x7c6c0  ldarg.1
0x7c6c1  callvirt instance class System.Xml.Serialization.ChoiceIdentifierAccessor System.Xml.Serialization.AccessorMapping::get_ChoiceIdentifier()
0x7c6c6  ldarg.3
0x7c6c7  callvirt instance class System.Xml.Serialization.XmlChoiceIdentifierAttribute System.Xml.Serialization.XmlAttributes::get_XmlChoiceIdentifier()
0x7c6cc  callvirt instance string System.Xml.Serialization.XmlChoiceIdentifierAttribute::get_MemberName()
0x7c6d1  callvirt instance void System.Xml.Serialization.ChoiceIdentifierAccessor::set_MemberName(string value)
0x7c6d6  ldarg.1
0x7c6d7  callvirt instance class System.Xml.Serialization.ChoiceIdentifierAccessor System.Xml.Serialization.AccessorMapping::get_ChoiceIdentifier()
0x7c6dc  ldarg.3
0x7c6dd  callvirt instance class System.Xml.Serialization.XmlChoiceIdentifierAttribute System.Xml.Serialization.XmlAttributes::get_XmlChoiceIdentifier()
0x7c6e2  callvirt instance class [mscorlib]System.Reflection.MemberInfo System.Xml.Serialization.XmlChoiceIdentifierAttribute::get_MemberInfo()
0x7c6e7  callvirt instance void System.Xml.Serialization.ChoiceIdentifierAccessor::set_MemberInfo(class [mscorlib]System.Reflection.MemberInfo value)
0x7c6ec  ldarg.1
0x7c6ed  callvirt instance class System.Xml.Serialization.ChoiceIdentifierAccessor System.Xml.Serialization.AccessorMapping::get_ChoiceIdentifier()
0x7c6f2  ldarg.0
0x7c6f3  ldarg.0
0x7c6f4  ldfld    class System.Xml.Serialization.ModelScope System.Xml.Serialization.XmlReflectionImporter::modelScope
0x7c6f9  ldarg.s  5
0x7c6fb  callvirt instance class System.Xml.Serialization.TypeModel System.Xml.Serialization.ModelScope::GetTypeModel(class [mscorlib]System.Type type)
0x7c700  ldarg.s  4
0x7c702  ldc.i4.2
0x7c703  ldsfld   string [mscorlib]System.String::Empty
0x7c708  ldnull
0x7c709  ldarg.s  8
0x7c70b  call     instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.XmlReflectionImporter::ImportTypeMapping(class System.Xml.Serialization.TypeModel model, string ns, valuetype ImportContext context, string dataType, class System.Xml.Serialization.XmlAttributes a, class System.Xml.Serialization.RecursionLimiter limiter)
0x7c710  callvirt instance void System.Xml.Serialization.Accessor::set_Mapping(class System.Xml.Serialization.TypeMapping value)
0x7c715  ldarg.0
0x7c716  ldarg.1
0x7c717  callvirt instance class System.Xml.Serialization.ChoiceIdentifierAccessor System.Xml.Serialization.AccessorMapping::get_ChoiceIdentifier()
0x7c71c  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7c721  castclass System.Xml.Serialization.EnumMapping
0x7c726  call     instance void System.Xml.Serialization.XmlReflectionImporter::CheckChoiceIdentifierMapping(class System.Xml.Serialization.EnumMapping choiceMapping)
0x7c72b  ldarg.1
0x7c72c  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x7c731  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsArrayLike()
0x7c736  brfalse  loc_7D1E9
0x7c73b  ldloc.s  5
0x7c73d  ldarg.2
0x7c73e  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.FieldModel::get_FieldTypeDesc()
0x7c743  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x7c748  ldstr    asc_129CEE// "."
0x7c74d  ldarg.2
0x7c74e  callvirt instance string System.Xml.Serialization.FieldModel::get_Name()
0x7c753  call     string [mscorlib]System.String::Concat(string, string, string)
0x7c758  call     class [mscorlib]System.Type System.Xml.Serialization.TypeScope::GetArrayElementType(class [mscorlib]System.Type type, string memberInfo)
0x7c75d  stloc.s  0xD
0x7c75f  ldloc.s  9
0x7c761  ldloc.s  0xB
0x7c763  and
0x7c764  brfalse  loc_7CA0C
0x7c769  ldloc.s  9
0x7c76b  ldloc.s  0xB
0x7c76d  and
0x7c76e  ldloc.s  9
0x7c770  beq.s    loc_7C782
0x7c772  ldstr    aXmlillegalattr_0// "XmlIllegalAttributesArrayAttribute"
0x7c777  call     string System.Xml.Res::GetString(string name)
0x7c77c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7c781  throw
0x7c782  ldarg.3
0x7c783  callvirt instance class System.Xml.Serialization.XmlAttributeAttribute System.Xml.Serialization.XmlAttributes::get_XmlAttribute()
0x7c788  brfalse  loc_7C839
0x7c78d  ldarg.1
0x7c78e  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x7c793  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_ArrayElementTypeDesc()
0x7c798  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsPrimitive()
0x7c79d  brtrue   loc_7C839
0x7c7a2  ldarg.1
0x7c7a3  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x7c7a8  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_ArrayElementTypeDesc()
0x7c7ad  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsEnum()
0x7c7b2  brtrue   loc_7C839
0x7c7b7  ldarg.1
0x7c7b8  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x7c7bd  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_ArrayElementTypeDesc()
0x7c7c2  callvirt instance valuetype System.Xml.Serialization.TypeKind System.Xml.Serialization.TypeDesc::get_Kind()
0x7c7c7  ldc.i4.s 0xB
0x7c7c9  bne.un.s loc_7C80B
0x7c7cb  ldstr    aXmlillegalattr_1// "XmlIllegalAttrOrTextInterface"
0x7c7d0  ldc.i4.3
0x7c7d1  newarr   [mscorlib]System.Object
0x7c7d6  dup
0x7c7d7  ldc.i4.0
0x7c7d8  ldloc.s  6
0x7c7da  stelem.ref
0x7c7db  dup
0x7c7dc  ldc.i4.1
0x7c7dd  ldarg.1
0x7c7de  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x7c7e3  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_ArrayElementTypeDesc()
0x7c7e8  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x7c7ed  stelem.ref
0x7c7ee  dup
0x7c7ef  ldc.i4.2
0x7c7f0  ldtoken  System.Xml.Serialization.IXmlSerializable
0x7c7f5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7c7fa  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7c7ff  stelem.ref
0x7c800  call     string System.Xml.Res::GetString(string name, object[] args)
0x7c805  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7c80a  throw
0x7c80b  ldstr    aXmlillegalattr_2// "XmlIllegalAttrOrText"
0x7c810  ldc.i4.2
0x7c811  newarr   [mscorlib]System.Object
0x7c816  dup
0x7c817  ldc.i4.0
0x7c818  ldloc.s  6
0x7c81a  stelem.ref
0x7c81b  dup
0x7c81c  ldc.i4.1
0x7c81d  ldarg.1
0x7c81e  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x7c823  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_ArrayElementTypeDesc()
0x7c828  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x7c82d  stelem.ref
0x7c82e  call     string System.Xml.Res::GetString(string name, object[] args)
0x7c833  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7c838  throw
0x7c839  ldarg.3
0x7c83a  callvirt instance class System.Xml.Serialization.XmlAttributeAttribute System.Xml.Serialization.XmlAttributes::get_XmlAttribute()
0x7c83f  brfalse.s loc_7C868
0x7c841  ldarg.1
0x7c842  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x7c847  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_ArrayElementTypeDesc()
0x7c84c  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsPrimitive()
0x7c851  brtrue.s loc_7C865
0x7c853  ldarg.1
0x7c854  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.AccessorMapping::get_TypeDesc()
0x7c859  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_ArrayElementTypeDesc()
0x7c85e  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsEnum()
0x7c863  br.s     loc_7C869
0x7c865  ldc.i4.1
0x7c866  br.s     loc_7C869
0x7c868  ldc.i4.0
0x7c869  stloc.s  0xE
0x7c86b  ldarg.3
0x7c86c  callvirt instance class System.Xml.Serialization.XmlAnyAttributeAttribute System.Xml.Serialization.XmlAttributes::get_XmlAnyAttribute()
0x7c871  brfalse.s loc_7C87E
0x7c873  ldarg.3
0x7c874  newobj   instance void System.Xml.Serialization.XmlAttributeAttribute::.ctor()
0x7c879  callvirt instance void System.Xml.Serialization.XmlAttributes::set_XmlAttribute(class System.Xml.Serialization.XmlAttributeAttribute value)
0x7c87e  newobj   instance void System.Xml.Serialization.AttributeAccessor::.ctor()
0x7c883  stloc.s  0xF
0x7c885  ldarg.3
0x7c886  callvirt instance class System.Xml.Serialization.XmlAttributeAttribute System.Xml.Serialization.XmlAttributes::get_XmlAttribute()
0x7c88b  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.XmlAttributeAttribute::get_Type()
0x7c890  ldnull
0x7c891  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7c896  brtrue.s loc_7C8A5
0x7c898  ldarg.3
0x7c899  callvirt instance class System.Xml.Serialization.XmlAttributeAttribute System.Xml.Serialization.XmlAttributes::get_XmlAttribute()
0x7c89e  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.XmlAttributeAttribute::get_Type()
0x7c8a3  br.s     loc_7C8A7
0x7c8a5  ldloc.s  0xD
0x7c8a7  stloc.s  0x10
0x7c8a9  ldarg.0
0x7c8aa  ldfld    class System.Xml.Serialization.TypeScope System.Xml.Serialization.XmlReflectionImporter::typeScope
0x7c8af  ldloc.s  0x10
0x7c8b1  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeScope::GetTypeDesc(class [mscorlib]System.Type type)
0x7c8b6  stloc.s  0x11
0x7c8b8  ldloc.s  0xF
0x7c8ba  ldarg.3
0x7c8bb  callvirt instance class System.Xml.Serialization.XmlAttributeAttribute System.Xml.Serialization.XmlAttributes::get_XmlAttribute()
0x7c8c0  callvirt instance string System.Xml.Serialization.XmlAttributeAttribute::get_AttributeName()
0x7c8c5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x7c8ca  brfalse.s loc_7C8D9
0x7c8cc  ldarg.3
0x7c8cd  callvirt instance class System.Xml.Serialization.XmlAttributeAttribute System.Xml.Serialization.XmlAttributes::get_XmlAttribute()
0x7c8d2  callvirt instance string System.Xml.Serialization.XmlAttributeAttribute::get_AttributeName()
0x7c8d7  br.s     loc_7C8DB
0x7c8d9  ldloc.s  6
0x7c8db  call     string System.Xml.Serialization.Accessor::EscapeQName(string name)
0x7c8e0  callvirt instance void System.Xml.Serialization.Accessor::set_Name(string value)
0x7c8e5  ldloc.s  0xF
0x7c8e7  ldarg.3
0x7c8e8  callvirt instance class System.Xml.Serialization.XmlAttributeAttribute System.Xml.Serialization.XmlAttributes::get_XmlAttribute()
0x7c8ed  callvirt instance string System.Xml.Serialization.XmlAttributeAttribute::get_Namespace()
0x7c8f2  brfalse.s loc_7C901
0x7c8f4  ldarg.3
0x7c8f5  callvirt instance class System.Xml.Serialization.XmlAttributeAttribute System.Xml.Serialization.XmlAttributes::get_XmlAttribute()
0x7c8fa  callvirt instance string System.Xml.Serialization.XmlAttributeAttribute::get_Namespace()
0x7c8ff  br.s     loc_7C903
0x7c901  ldarg.s  4
0x7c903  callvirt instance void System.Xml.Serialization.Accessor::set_Namespace(string value)
0x7c908  ldloc.s  0xF
0x7c90a  ldarg.3
0x7c90b  callvirt instance class System.Xml.Serialization.XmlAttributeAttribute System.Xml.Serialization.XmlAttributes::get_XmlAttribute()
0x7c910  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.XmlAttributeAttribute::get_Form()
0x7c915  callvirt instance void System.Xml.Serialization.Accessor::set_Form(valuetype System.Xml.Schema.XmlSchemaForm value)
0x7c91a  ldloc.s  0xF
0x7c91c  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0x7c921  brtrue.s loc_7C93B
0x7c923  ldarg.s  4
0x7c925  ldloc.s  0xF
0x7c927  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x7c92c  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x7c931  brfalse.s loc_7C93B
0x7c933  ldloc.s  0xF
0x7c935  ldc.i4.1
0x7c936  callvirt instance void System.Xml.Serialization.Accessor::set_Form(valuetype System.Xml.Schema.XmlSchemaForm value)
0x7c93b  ldloc.s  0xF
0x7c93d  callvirt instance void System.Xml.Serialization.AttributeAccessor::CheckSpecial()
0x7c942  ldloc.s  0xF
0x7c944  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0x7c949  ldarg.s  4
0x7c94b  ldloc.s  0xF
0x7c94d  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x7c952  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x7c957  call     void System.Xml.Serialization.XmlReflectionImporter::CheckForm(valuetype System.Xml.Schema.XmlSchemaForm form, bool isQualified)
0x7c95c  ldloc.s  0xF
0x7c95e  ldarg.0
0x7c95f  ldarg.0
0x7c960  ldfld    class System.Xml.Serialization.ModelScope System.Xml.Serialization.XmlReflectionImporter::modelScope
0x7c965  ldloc.s  0x10
0x7c967  callvirt instance class System.Xml.Serialization.TypeModel System.Xml.Serialization.ModelScope::GetTypeModel(class [mscorlib]System.Type type)
0x7c96c  ldarg.s  4
  ... truncated ...
```
