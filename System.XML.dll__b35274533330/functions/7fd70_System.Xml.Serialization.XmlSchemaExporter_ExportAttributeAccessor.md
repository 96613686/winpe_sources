# System.Xml.Serialization.XmlSchemaExporter::ExportAttributeAccessor

- ea: `0x7fd70`
- end: `0x80139`
- name: `System.Xml.Serialization.XmlSchemaExporter::ExportAttributeAccessor`
- size: `969`
- prototype: ``
- caller_count: `1`
- callee_count: `48`
- tags: `registry_config`

## callers

- `0x808d0`

## callees

- `0x132e0`
- `0x622f0`
- `0x62370`
- `0x68600`
- `0x68620`
- `0x68640`
- `0x68660`
- `0x68690`
- `0x686d0`
- `0x686f0`
- `0x68a50`
- `0x68c50`
- `0x68c90`
- `0x68cd0`
- `0x72c20`
- `0x7f340`
- `0x7f3f0`
- `0x7fb30`
- `0x7fb70`
- `0x7fd70`
- `0x80380`
- `0x84b80`
- `0xcfcb0`
- `0xd0830`
- `0xd08d0`
- `0xd0910`
- `0xd0930`
- `0xd0950`
- `0xd0980`
- `0xd09b0`
- `0xd09d0`
- `0xd0b50`
- `0xd15b0`
- `0xd15d0`
- `0xd1670`
- `0xd1690`
- `0xd1990`
- `0xd19d0`
- `0xd1a00`
- `0xd2160`
- `0xd3f00`
- `0xd6540`
- `0xd6560`
- `0xd6690`
- `0xd66b0`
- `0xd6770`
- `0xd67a0`
- `0xd67f0`

## string_xrefs

- `0x7fe3e`: `http://www.w3.org/XML/1998/namespace`
- `0x7fe5e`: `http://www.w3.org/XML/1998/namespace`
- `0x80108`: `XmlInternalError`
- `0x7fe00`: `XmlInvalidContent`

## pseudocode

```c

```

## disassembly

```asm
0x7fd70  ldarg.2
0x7fd71  brtrue.s loc_7FD74
0x7fd73  ret
0x7fd74  ldarg.1
0x7fd75  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x7fd7a  brfalse  loc_7FE2E
0x7fd7f  ldarg.1
0x7fd80  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x7fd85  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x7fd8a  isinst   System.Xml.Schema.XmlSchemaComplexContentRestriction
0x7fd8f  brfalse.s loc_7FDAC
0x7fd91  ldarg.1
0x7fd92  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x7fd97  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x7fd9c  castclass System.Xml.Schema.XmlSchemaComplexContentRestriction
0x7fda1  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaComplexContentRestriction::get_Attributes()
0x7fda6  stloc.0
0x7fda7  br       loc_7FE35
0x7fdac  ldarg.1
0x7fdad  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x7fdb2  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x7fdb7  isinst   System.Xml.Schema.XmlSchemaComplexContentExtension
0x7fdbc  brfalse.s loc_7FDD6
0x7fdbe  ldarg.1
0x7fdbf  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x7fdc4  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x7fdc9  castclass System.Xml.Schema.XmlSchemaComplexContentExtension
0x7fdce  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaComplexContentExtension::get_Attributes()
0x7fdd3  stloc.0
0x7fdd4  br.s     loc_7FE35
0x7fdd6  ldarg.1
0x7fdd7  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x7fddc  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x7fde1  isinst   System.Xml.Schema.XmlSchemaSimpleContentExtension
0x7fde6  brfalse.s loc_7FE00
0x7fde8  ldarg.1
0x7fde9  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x7fdee  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x7fdf3  castclass System.Xml.Schema.XmlSchemaSimpleContentExtension
0x7fdf8  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaSimpleContentExtension::get_Attributes()
0x7fdfd  stloc.0
0x7fdfe  br.s     loc_7FE35
0x7fe00  ldstr    aXmlinvalidcont// "XmlInvalidContent"
0x7fe05  ldc.i4.1
0x7fe06  newarr   [mscorlib]System.Object
0x7fe0b  dup
0x7fe0c  ldc.i4.0
0x7fe0d  ldarg.1
0x7fe0e  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x7fe13  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x7fe18  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x7fe1d  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7fe22  stelem.ref
0x7fe23  call     string System.Xml.Res::GetString(string name, object[] args)
0x7fe28  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7fe2d  throw
0x7fe2e  ldarg.1
0x7fe2f  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaComplexType::get_Attributes()
0x7fe34  stloc.0
0x7fe35  ldarg.2
0x7fe36  callvirt instance bool System.Xml.Serialization.AttributeAccessor::get_IsSpecialXmlNamespace()
0x7fe3b  brfalse.s loc_7FE76
0x7fe3d  ldarg.0
0x7fe3e  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x7fe43  ldarg.s  4
0x7fe45  call     instance void System.Xml.Serialization.XmlSchemaExporter::AddSchemaImport(string ns, string referencingNs)
0x7fe4a  newobj   instance void System.Xml.Schema.XmlSchemaAttribute::.ctor()
0x7fe4f  stloc.1
0x7fe50  ldloc.1
0x7fe51  ldc.i4.1
0x7fe52  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_Use(valuetype System.Xml.Schema.XmlSchemaUse value)
0x7fe57  ldloc.1
0x7fe58  ldarg.2
0x7fe59  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x7fe5e  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x7fe63  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x7fe68  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_RefName(class System.Xml.XmlQualifiedName value)
0x7fe6d  ldloc.0
0x7fe6e  ldloc.1
0x7fe6f  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0x7fe74  pop
0x7fe75  ret
0x7fe76  ldarg.2
0x7fe77  callvirt instance bool System.Xml.Serialization.Accessor::get_Any()
0x7fe7c  brfalse  loc_7FF03
0x7fe81  ldarg.1
0x7fe82  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x7fe87  brtrue.s loc_7FE95
0x7fe89  ldarg.1
0x7fe8a  newobj   instance void System.Xml.Schema.XmlSchemaAnyAttribute::.ctor()
0x7fe8f  callvirt instance void System.Xml.Schema.XmlSchemaComplexType::set_AnyAttribute(class System.Xml.Schema.XmlSchemaAnyAttribute value)
0x7fe94  ret
0x7fe95  ldarg.1
0x7fe96  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x7fe9b  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x7fea0  stloc.2
0x7fea1  ldloc.2
0x7fea2  isinst   System.Xml.Schema.XmlSchemaComplexContentExtension
0x7fea7  brfalse.s loc_7FEBC
0x7fea9  ldloc.2
0x7feaa  castclass System.Xml.Schema.XmlSchemaComplexContentExtension
0x7feaf  stloc.3
0x7feb0  ldloc.3
0x7feb1  newobj   instance void System.Xml.Schema.XmlSchemaAnyAttribute::.ctor()
0x7feb6  callvirt instance void System.Xml.Schema.XmlSchemaComplexContentExtension::set_AnyAttribute(class System.Xml.Schema.XmlSchemaAnyAttribute value)
0x7febb  ret
0x7febc  ldloc.2
0x7febd  isinst   System.Xml.Schema.XmlSchemaComplexContentRestriction
0x7fec2  brfalse.s loc_7FED9
0x7fec4  ldloc.2
0x7fec5  castclass System.Xml.Schema.XmlSchemaComplexContentRestriction
0x7feca  stloc.s  4
0x7fecc  ldloc.s  4
0x7fece  newobj   instance void System.Xml.Schema.XmlSchemaAnyAttribute::.ctor()
0x7fed3  callvirt instance void System.Xml.Schema.XmlSchemaComplexContentRestriction::set_AnyAttribute(class System.Xml.Schema.XmlSchemaAnyAttribute value)
0x7fed8  ret
0x7fed9  ldarg.1
0x7feda  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x7fedf  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x7fee4  isinst   System.Xml.Schema.XmlSchemaSimpleContentExtension
0x7fee9  brfalse  loc_80138
0x7feee  ldloc.2
0x7feef  castclass System.Xml.Schema.XmlSchemaSimpleContentExtension
0x7fef4  stloc.s  5
0x7fef6  ldloc.s  5
0x7fef8  newobj   instance void System.Xml.Schema.XmlSchemaAnyAttribute::.ctor()
0x7fefd  callvirt instance void System.Xml.Schema.XmlSchemaSimpleContentExtension::set_AnyAttribute(class System.Xml.Schema.XmlSchemaAnyAttribute value)
0x7ff02  ret
0x7ff03  newobj   instance void System.Xml.Schema.XmlSchemaAttribute::.ctor()
0x7ff08  stloc.s  6
0x7ff0a  ldloc.s  6
0x7ff0c  ldc.i4.0
0x7ff0d  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_Use(valuetype System.Xml.Schema.XmlSchemaUse value)
0x7ff12  ldarg.2
0x7ff13  callvirt instance bool System.Xml.Serialization.Accessor::get_HasDefault()
0x7ff18  brtrue.s loc_7FF37
0x7ff1a  ldarg.3
0x7ff1b  brtrue.s loc_7FF37
0x7ff1d  ldarg.2
0x7ff1e  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x7ff23  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x7ff28  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsValueType()
0x7ff2d  brfalse.s loc_7FF37
0x7ff2f  ldloc.s  6
0x7ff31  ldc.i4.3
0x7ff32  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_Use(valuetype System.Xml.Schema.XmlSchemaUse value)
0x7ff37  ldloc.s  6
0x7ff39  ldarg.2
0x7ff3a  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x7ff3f  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_Name(string value)
0x7ff44  ldarg.2
0x7ff45  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x7ff4a  brfalse.s loc_7FF5B
0x7ff4c  ldarg.2
0x7ff4d  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x7ff52  ldarg.s  4
0x7ff54  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7ff59  brfalse.s loc_7FFB3
0x7ff5b  ldarg.0
0x7ff5c  ldfld    class System.Xml.Serialization.XmlSchemas System.Xml.Serialization.XmlSchemaExporter::schemas
0x7ff61  ldarg.s  4
0x7ff63  callvirt instance class System.Xml.Schema.XmlSchema System.Xml.Serialization.XmlSchemas::get_Item(string ns)
0x7ff68  stloc.s  7
0x7ff6a  ldloc.s  7
0x7ff6c  brtrue.s loc_7FF89
0x7ff6e  ldloc.s  6
0x7ff70  ldarg.2
0x7ff71  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0x7ff76  ldc.i4.2
0x7ff77  beq.s    loc_7FF81
0x7ff79  ldarg.2
0x7ff7a  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0x7ff7f  br.s     loc_7FF82
0x7ff81  ldc.i4.0
0x7ff82  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_Form(valuetype System.Xml.Schema.XmlSchemaForm value)
0x7ff87  br.s     loc_7FFA8
0x7ff89  ldloc.s  6
0x7ff8b  ldarg.2
0x7ff8c  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0x7ff91  ldloc.s  7
0x7ff93  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Schema.XmlSchema::get_AttributeFormDefault()
0x7ff98  beq.s    loc_7FFA2
0x7ff9a  ldarg.2
0x7ff9b  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0x7ffa0  br.s     loc_7FFA3
0x7ffa2  ldc.i4.0
0x7ffa3  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_Form(valuetype System.Xml.Schema.XmlSchemaForm value)
0x7ffa8  ldloc.0
0x7ffa9  ldloc.s  6
0x7ffab  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0x7ffb0  pop
0x7ffb1  br.s     loc_80031
0x7ffb3  ldarg.0
0x7ffb4  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSchemaExporter::attributes
0x7ffb9  ldarg.2
0x7ffba  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x7ffbf  brtrue.s loc_7FFF3
0x7ffc1  ldloc.s  6
0x7ffc3  ldc.i4.0
0x7ffc4  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_Use(valuetype System.Xml.Schema.XmlSchemaUse value)
0x7ffc9  ldloc.s  6
0x7ffcb  ldarg.2
0x7ffcc  callvirt instance valuetype System.Xml.Schema.XmlSchemaForm System.Xml.Serialization.Accessor::get_Form()
0x7ffd1  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_Form(valuetype System.Xml.Schema.XmlSchemaForm value)
0x7ffd6  ldarg.0
0x7ffd7  ldloc.s  6
0x7ffd9  ldarg.2
0x7ffda  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x7ffdf  ldarg.s  4
0x7ffe1  call     instance void System.Xml.Serialization.XmlSchemaExporter::AddSchemaItem(class System.Xml.Schema.XmlSchemaObject item, string ns, string referencingNs)
0x7ffe6  ldarg.0
0x7ffe7  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSchemaExporter::attributes
0x7ffec  ldarg.2
0x7ffed  ldarg.2
0x7ffee  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x7fff3  newobj   instance void System.Xml.Schema.XmlSchemaAttribute::.ctor()
0x7fff8  stloc.s  8
0x7fffa  ldloc.s  8
0x7fffc  ldc.i4.0
0x7fffd  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_Use(valuetype System.Xml.Schema.XmlSchemaUse value)
0x80002  ldloc.s  8
0x80004  ldarg.2
0x80005  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x8000a  ldarg.2
0x8000b  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x80010  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x80015  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_RefName(class System.Xml.XmlQualifiedName value)
0x8001a  ldloc.0
0x8001b  ldloc.s  8
0x8001d  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0x80022  pop
0x80023  ldarg.0
0x80024  ldarg.2
0x80025  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x8002a  ldarg.s  4
0x8002c  call     instance void System.Xml.Serialization.XmlSchemaExporter::AddSchemaImport(string ns, string referencingNs)
0x80031  ldarg.2
0x80032  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x80037  isinst   System.Xml.Serialization.PrimitiveMapping
0x8003c  brfalse  loc_800FB
0x80041  ldarg.2
0x80042  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x80047  castclass System.Xml.Serialization.PrimitiveMapping
0x8004c  stloc.s  9
0x8004e  ldloc.s  9
0x80050  callvirt instance bool System.Xml.Serialization.TypeMapping::get_IsList()
0x80055  brfalse.s loc_800B9
0x80057  newobj   instance void System.Xml.Schema.XmlSchemaSimpleType::.ctor()
0x8005c  stloc.s  0xA
0x8005e  newobj   instance void System.Xml.Schema.XmlSchemaSimpleTypeList::.ctor()
0x80063  stloc.s  0xB
0x80065  ldloc.s  9
0x80067  callvirt instance bool System.Xml.Serialization.TypeMapping::get_IsAnonymousType()
0x8006c  brfalse.s loc_80084
0x8006e  ldloc.s  0xB
0x80070  ldarg.0
0x80071  ldloc.s  9
0x80073  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.XmlSchemaExporter::ExportAnonymousPrimitiveMapping(class System.Xml.Serialization.PrimitiveMapping mapping)
0x80078  castclass System.Xml.Schema.XmlSchemaSimpleType
0x8007d  callvirt instance void System.Xml.Schema.XmlSchemaSimpleTypeList::set_ItemType(class System.Xml.Schema.XmlSchemaSimpleType value)
0x80082  br.s     loc_800A5
0x80084  ldloc.s  0xB
0x80086  ldarg.0
0x80087  ldloc.s  9
0x80089  ldarg.2
0x8008a  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x8008f  brfalse.s loc_80099
0x80091  ldarg.2
0x80092  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x80097  br.s     loc_8009B
0x80099  ldarg.s  4
0x8009b  call     instance class System.Xml.XmlQualifiedName System.Xml.Serialization.XmlSchemaExporter::ExportPrimitiveMapping(class System.Xml.Serialization.PrimitiveMapping mapping, string ns)
0x800a0  callvirt instance void System.Xml.Schema.XmlSchemaSimpleTypeList::set_ItemTypeName(class System.Xml.XmlQualifiedName value)
0x800a5  ldloc.s  0xA
0x800a7  ldloc.s  0xB
0x800a9  callvirt instance void System.Xml.Schema.XmlSchemaSimpleType::set_Content(class System.Xml.Schema.XmlSchemaSimpleTypeContent value)
0x800ae  ldloc.s  6
0x800b0  ldloc.s  0xA
0x800b2  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_SchemaType(class System.Xml.Schema.XmlSchemaSimpleType value)
0x800b7  br.s     loc_80118
0x800b9  ldloc.s  9
0x800bb  callvirt instance bool System.Xml.Serialization.TypeMapping::get_IsAnonymousType()
0x800c0  brfalse.s loc_800D8
0x800c2  ldloc.s  6
0x800c4  ldarg.0
0x800c5  ldloc.s  9
0x800c7  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.XmlSchemaExporter::ExportAnonymousPrimitiveMapping(class System.Xml.Serialization.PrimitiveMapping mapping)
0x800cc  castclass System.Xml.Schema.XmlSchemaSimpleType
0x800d1  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_SchemaType(class System.Xml.Schema.XmlSchemaSimpleType value)
0x800d6  br.s     loc_80118
0x800d8  ldloc.s  6
0x800da  ldarg.0
0x800db  ldloc.s  9
0x800dd  ldarg.2
0x800de  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x800e3  brfalse.s loc_800ED
0x800e5  ldarg.2
0x800e6  callvirt instance string System.Xml.Serialization.Accessor::get_Namespace()
0x800eb  br.s     loc_800EF
0x800ed  ldarg.s  4
  ... truncated ...
```
