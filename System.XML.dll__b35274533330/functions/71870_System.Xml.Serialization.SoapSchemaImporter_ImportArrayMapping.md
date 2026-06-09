# System.Xml.Serialization.SoapSchemaImporter::ImportArrayMapping

- ea: `0x71870`
- end: `0x71bec`
- name: `System.Xml.Serialization.SoapSchemaImporter::ImportArrayMapping`
- size: `892`
- prototype: ``
- caller_count: `2`
- callee_count: `42`
- tags: `registry_config`

## callers

- `0x712a0`
- `0x71810`

## callees

- `0x13310`
- `0x13320`
- `0x51110`
- `0x51cb0`
- `0x51ce0`
- `0x65420`
- `0x68600`
- `0x68610`
- `0x68680`
- `0x686e0`
- `0x68700`
- `0x688a0`
- `0x688c0`
- `0x68970`
- `0x68c30`
- `0x68c40`
- `0x68c50`
- `0x68c60`
- `0x68d50`
- `0x68dd0`
- `0x68e80`
- `0x6b380`
- `0x6b500`
- `0x70f20`
- `0x711f0`
- `0x71870`
- `0x72be0`
- `0x72e20`
- `0x73000`
- `0x73d30`
- `0x74e70`
- `0xd0370`
- `0xd0940`
- `0xd1650`
- `0xd1670`
- `0xd1990`
- `0xd2160`
- `0xd36a0`
- `0xd3eb0`
- `0xd4530`
- `0xd6af0`
- `0xd6cf0`

## string_xrefs

- `0x71886`: `http://schemas.xmlsoap.org/soap/encoding/`
- `0x7194c`: `http://schemas.xmlsoap.org/soap/encoding/`
- `0x719d1`: `http://schemas.xmlsoap.org/soap/encoding/`
- `0x71a1b`: `http://schemas.xmlsoap.org/wsdl/`

## pseudocode

```c

```

## disassembly

```asm
0x71870  ldarg.1
0x71871  callvirt instance string System.Xml.Schema.XmlSchemaType::get_Name()
0x71876  ldstr    aArray_0// "Array"
0x7187b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x71880  brfalse  loc_7192A
0x71885  ldarg.2
0x71886  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/encodin"...
0x7188b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x71890  brfalse  loc_7192A
0x71895  newobj   instance void System.Xml.Serialization.ArrayMapping::.ctor()
0x7189a  stloc.0
0x7189b  ldarg.0
0x7189c  call     instance class System.Xml.Serialization.StructMapping System.Xml.Serialization.SchemaImporter::GetRootMapping()
0x718a1  stloc.s  4
0x718a3  newobj   instance void System.Xml.Serialization.ElementAccessor::.ctor()
0x718a8  stloc.s  5
0x718aa  ldloc.s  5
0x718ac  ldc.i4.1
0x718ad  callvirt instance void System.Xml.Serialization.ElementAccessor::set_IsSoap(bool value)
0x718b2  ldloc.s  5
0x718b4  ldstr    aAnytype// "anyType"
0x718b9  callvirt instance void System.Xml.Serialization.Accessor::set_Name(string value)
0x718be  ldloc.s  5
0x718c0  ldarg.2
0x718c1  callvirt instance void System.Xml.Serialization.Accessor::set_Namespace(string value)
0x718c6  ldloc.s  5
0x718c8  ldloc.s  4
0x718ca  callvirt instance void System.Xml.Serialization.Accessor::set_Mapping(class System.Xml.Serialization.TypeMapping value)
0x718cf  ldloc.s  5
0x718d1  ldc.i4.1
0x718d2  callvirt instance void System.Xml.Serialization.ElementAccessor::set_IsNullable(bool value)
0x718d7  ldloc.s  5
0x718d9  ldc.i4.0
0x718da  callvirt instance void System.Xml.Serialization.Accessor::set_Form(valuetype System.Xml.Schema.XmlSchemaForm value)
0x718df  ldloc.0
0x718e0  ldc.i4.1
0x718e1  newarr   System.Xml.Serialization.ElementAccessor
0x718e6  dup
0x718e7  ldc.i4.0
0x718e8  ldloc.s  5
0x718ea  stelem.ref
0x718eb  callvirt instance void System.Xml.Serialization.ArrayMapping::set_Elements(class System.Xml.Serialization.ElementAccessor[] value)
0x718f0  ldloc.0
0x718f1  ldloc.s  5
0x718f3  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x718f8  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x718fd  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::CreateArrayTypeDesc()
0x71902  callvirt instance void System.Xml.Serialization.TypeMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x71907  ldloc.0
0x71908  ldstr    aArrayof// "ArrayOf"
0x7190d  ldloc.s  5
0x7190f  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x71914  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x71919  call     string System.Xml.Serialization.CodeIdentifier::MakePascal(string identifier)
0x7191e  call     string [mscorlib]System.String::Concat(string, string)
0x71923  callvirt instance void System.Xml.Serialization.TypeMapping::set_TypeName(string value)
0x71928  ldloc.0
0x71929  ret
0x7192a  ldarg.1
0x7192b  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_DerivedFrom()
0x71930  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x71935  ldstr    aArray_0// "Array"
0x7193a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7193f  brfalse.s loc_71958
0x71941  ldarg.1
0x71942  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_DerivedFrom()
0x71947  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x7194c  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/encodin"...
0x71951  call     bool [mscorlib]System.String::op_Equality(string, string)
0x71956  brtrue.s loc_7195A
0x71958  ldnull
0x71959  ret
0x7195a  ldarg.1
0x7195b  castclass System.Xml.Schema.XmlSchemaComplexType
0x71960  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x71965  stloc.1
0x71966  ldloc.1
0x71967  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x7196c  isinst   System.Xml.Schema.XmlSchemaComplexContentRestriction
0x71971  brtrue.s loc_71975
0x71973  ldnull
0x71974  ret
0x71975  newobj   instance void System.Xml.Serialization.ArrayMapping::.ctor()
0x7197a  stloc.0
0x7197b  ldloc.1
0x7197c  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x71981  castclass System.Xml.Schema.XmlSchemaComplexContentRestriction
0x71986  stloc.2
0x71987  ldc.i4.0
0x71988  stloc.s  6
0x7198a  br       loc_71B3B
0x7198f  ldloc.2
0x71990  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaComplexContentRestriction::get_Attributes()
0x71995  ldloc.s  6
0x71997  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0x7199c  isinst   System.Xml.Schema.XmlSchemaAttribute
0x719a1  stloc.s  7
0x719a3  ldloc.s  7
0x719a5  brfalse  loc_71B35
0x719aa  ldloc.s  7
0x719ac  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaAttribute::get_RefName()
0x719b1  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x719b6  ldstr    aArraytype// "arrayType"
0x719bb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x719c0  brfalse  loc_71B35
0x719c5  ldloc.s  7
0x719c7  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaAttribute::get_RefName()
0x719cc  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x719d1  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/encodin"...
0x719d6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x719db  brfalse  loc_71B35
0x719e0  ldnull
0x719e1  stloc.s  8
0x719e3  ldloc.s  7
0x719e5  callvirt instance class System.Xml.XmlAttribute[] System.Xml.Schema.XmlSchemaAnnotated::get_UnhandledAttributes()
0x719ea  brfalse.s loc_71A40
0x719ec  ldloc.s  7
0x719ee  callvirt instance class System.Xml.XmlAttribute[] System.Xml.Schema.XmlSchemaAnnotated::get_UnhandledAttributes()
0x719f3  stloc.s  9
0x719f5  ldc.i4.0
0x719f6  stloc.s  0xA
0x719f8  br.s     loc_71A38
0x719fa  ldloc.s  9
0x719fc  ldloc.s  0xA
0x719fe  ldelem.ref
0x719ff  stloc.s  0xB
0x71a01  ldloc.s  0xB
0x71a03  callvirt instance string System.Xml.XmlNode::get_LocalName()
0x71a08  ldstr    aArraytype// "arrayType"
0x71a0d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x71a12  brfalse.s loc_71A32
0x71a14  ldloc.s  0xB
0x71a16  callvirt instance string System.Xml.XmlNode::get_NamespaceURI()
0x71a1b  ldstr    aHttpSchemasXml_0// "http://schemas.xmlsoap.org/wsdl/"
0x71a20  call     bool [mscorlib]System.String::op_Equality(string, string)
0x71a25  brfalse.s loc_71A32
0x71a27  ldloc.s  0xB
0x71a29  callvirt instance string System.Xml.XmlNode::get_Value()
0x71a2e  stloc.s  8
0x71a30  br.s     loc_71A40
0x71a32  ldloc.s  0xA
0x71a34  ldc.i4.1
0x71a35  add
0x71a36  stloc.s  0xA
0x71a38  ldloc.s  0xA
0x71a3a  ldloc.s  9
0x71a3c  ldlen
0x71a3d  conv.i4
0x71a3e  blt.s    loc_719FA
0x71a40  ldloc.s  8
0x71a42  brfalse  loc_71B35
0x71a47  ldloc.s  8
0x71a49  ldloca.s 0xC
0x71a4b  ldloc.s  7
0x71a4d  call     class System.Xml.XmlQualifiedName System.Xml.Serialization.TypeScope::ParseWsdlArrayType(string type, [out] string& dims, class System.Xml.Schema.XmlSchemaObject parent)
0x71a52  stloc.s  0xD
0x71a54  ldarg.0
0x71a55  call     instance class System.Xml.Serialization.TypeScope System.Xml.Serialization.SchemaImporter::get_Scope()
0x71a5a  ldloc.s  0xD
0x71a5c  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x71a61  ldloc.s  0xD
0x71a63  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x71a68  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeScope::GetTypeDesc(string name, string ns)
0x71a6d  stloc.s  0xF
0x71a6f  ldloc.s  0xF
0x71a71  brfalse.s loc_71AA1
0x71a73  ldloc.s  0xF
0x71a75  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsPrimitive()
0x71a7a  brfalse.s loc_71AA1
0x71a7c  newobj   instance void System.Xml.Serialization.PrimitiveMapping::.ctor()
0x71a81  stloc.s  0xE
0x71a83  ldloc.s  0xE
0x71a85  ldloc.s  0xF
0x71a87  callvirt instance void System.Xml.Serialization.TypeMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x71a8c  ldloc.s  0xE
0x71a8e  ldloc.s  0xF
0x71a90  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.TypeDesc::get_DataType()
0x71a95  callvirt instance string System.Xml.Schema.XmlSchemaType::get_Name()
0x71a9a  callvirt instance void System.Xml.Serialization.TypeMapping::set_TypeName(string value)
0x71a9f  br.s     loc_71AAC
0x71aa1  ldarg.0
0x71aa2  ldloc.s  0xD
0x71aa4  ldc.i4.0
0x71aa5  call     instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.SoapSchemaImporter::ImportType(class System.Xml.XmlQualifiedName name, bool excludeFromImport)
0x71aaa  stloc.s  0xE
0x71aac  newobj   instance void System.Xml.Serialization.ElementAccessor::.ctor()
0x71ab1  stloc.s  0x10
0x71ab3  ldloc.s  0x10
0x71ab5  ldc.i4.1
0x71ab6  callvirt instance void System.Xml.Serialization.ElementAccessor::set_IsSoap(bool value)
0x71abb  ldloc.s  0x10
0x71abd  ldloc.s  0xD
0x71abf  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x71ac4  callvirt instance void System.Xml.Serialization.Accessor::set_Name(string value)
0x71ac9  ldloc.s  0x10
0x71acb  ldarg.2
0x71acc  callvirt instance void System.Xml.Serialization.Accessor::set_Namespace(string value)
0x71ad1  ldloc.s  0x10
0x71ad3  ldloc.s  0xE
0x71ad5  callvirt instance void System.Xml.Serialization.Accessor::set_Mapping(class System.Xml.Serialization.TypeMapping value)
0x71ada  ldloc.s  0x10
0x71adc  ldc.i4.1
0x71add  callvirt instance void System.Xml.Serialization.ElementAccessor::set_IsNullable(bool value)
0x71ae2  ldloc.s  0x10
0x71ae4  ldc.i4.0
0x71ae5  callvirt instance void System.Xml.Serialization.Accessor::set_Form(valuetype System.Xml.Schema.XmlSchemaForm value)
0x71aea  ldloc.0
0x71aeb  ldc.i4.1
0x71aec  newarr   System.Xml.Serialization.ElementAccessor
0x71af1  dup
0x71af2  ldc.i4.0
0x71af3  ldloc.s  0x10
0x71af5  stelem.ref
0x71af6  callvirt instance void System.Xml.Serialization.ArrayMapping::set_Elements(class System.Xml.Serialization.ElementAccessor[] value)
0x71afb  ldloc.0
0x71afc  ldloc.s  0x10
0x71afe  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x71b03  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x71b08  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::CreateArrayTypeDesc()
0x71b0d  callvirt instance void System.Xml.Serialization.TypeMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x71b12  ldloc.0
0x71b13  ldstr    aArrayof// "ArrayOf"
0x71b18  ldloc.s  0x10
0x71b1a  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x71b1f  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x71b24  call     string System.Xml.Serialization.CodeIdentifier::MakePascal(string identifier)
0x71b29  call     string [mscorlib]System.String::Concat(string, string)
0x71b2e  callvirt instance void System.Xml.Serialization.TypeMapping::set_TypeName(string value)
0x71b33  ldloc.0
0x71b34  ret
0x71b35  ldloc.s  6
0x71b37  ldc.i4.1
0x71b38  add
0x71b39  stloc.s  6
0x71b3b  ldloc.s  6
0x71b3d  ldloc.2
0x71b3e  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaComplexContentRestriction::get_Attributes()
0x71b43  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x71b48  blt      loc_7198F
0x71b4d  ldloc.2
0x71b4e  callvirt instance class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.XmlSchemaComplexContentRestriction::get_Particle()
0x71b53  stloc.3
0x71b54  ldloc.3
0x71b55  isinst   System.Xml.Schema.XmlSchemaAll
0x71b5a  brtrue.s loc_71B67
0x71b5c  ldloc.3
0x71b5d  isinst   System.Xml.Schema.XmlSchemaSequence
0x71b62  brfalse  loc_71BE8
0x71b67  ldloc.3
0x71b68  castclass System.Xml.Schema.XmlSchemaGroupBase
0x71b6d  stloc.s  0x11
0x71b6f  ldloc.s  0x11
0x71b71  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x71b76  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x71b7b  ldc.i4.1
0x71b7c  bne.un.s loc_71B92
0x71b7e  ldloc.s  0x11
0x71b80  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x71b85  ldc.i4.0
0x71b86  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0x71b8b  isinst   System.Xml.Schema.XmlSchemaElement
0x71b90  brtrue.s loc_71B94
0x71b92  ldnull
0x71b93  ret
0x71b94  ldloc.s  0x11
0x71b96  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x71b9b  ldc.i4.0
0x71b9c  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0x71ba1  castclass System.Xml.Schema.XmlSchemaElement
0x71ba6  stloc.s  0x12
0x71ba8  ldloc.s  0x12
0x71baa  callvirt instance bool System.Xml.Schema.XmlSchemaParticle::get_IsMultipleOccurrence()
0x71baf  brtrue.s loc_71BB3
0x71bb1  ldnull
0x71bb2  ret
0x71bb3  ldarg.0
0x71bb4  ldloc.s  0x12
0x71bb6  ldarg.2
0x71bb7  call     instance class System.Xml.Serialization.ElementAccessor System.Xml.Serialization.SoapSchemaImporter::ImportElement(class System.Xml.Schema.XmlSchemaElement element, string ns)
0x71bbc  stloc.s  0x13
0x71bbe  ldloc.0
0x71bbf  ldc.i4.1
0x71bc0  newarr   System.Xml.Serialization.ElementAccessor
0x71bc5  dup
0x71bc6  ldc.i4.0
0x71bc7  ldloc.s  0x13
0x71bc9  stelem.ref
0x71bca  callvirt instance void System.Xml.Serialization.ArrayMapping::set_Elements(class System.Xml.Serialization.ElementAccessor[] value)
0x71bcf  ldloc.0
0x71bd0  ldloc.s  0x13
0x71bd2  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x71bd7  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x71bdc  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::CreateArrayTypeDesc()
0x71be1  callvirt instance void System.Xml.Serialization.TypeMapping::set_TypeDesc(class System.Xml.Serialization.TypeDesc value)
0x71be6  br.s     loc_71BEA
0x71be8  ldnull
0x71be9  ret
0x71bea  ldloc.0
0x71beb  ret
```
