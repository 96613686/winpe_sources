# System.Xml.Serialization.XmlReflectionImporter::ImportTypeMapping_4

- ea: `0x7a2a0`
- end: `0x7a63f`
- name: `System.Xml.Serialization.XmlReflectionImporter::ImportTypeMapping_4`
- size: `927`
- prototype: ``
- caller_count: `3`
- callee_count: `30`
- tags: `registry_config`

## callers

- `0x7a280`
- `0x7a2a0`
- `0x7c5e0`

## callees

- `0x132e0`
- `0x622f0`
- `0x6a6b0`
- `0x6a800`
- `0x6a820`
- `0x72b80`
- `0x72b90`
- `0x72be0`
- `0x72bf0`
- `0x72c10`
- `0x72ca0`
- `0x72d70`
- `0x72e20`
- `0x730b0`
- `0x73d30`
- `0x74510`
- `0x75770`
- `0x79cc0`
- `0x7a230`
- `0x7a2a0`
- `0x7a790`
- `0x7aae0`
- `0x7ab00`
- `0x7ab80`
- `0x7ad20`
- `0x7adb0`
- `0x7b880`
- `0x7ba80`
- `0x7bb40`
- `0xd6af0`

## string_xrefs

- `0x7a301`: `http://www.w3.org/2001/XMLSchema`
- `0x7a32b`: `http://www.w3.org/2001/XMLSchema`
- `0x7a4bc`: `http://www.w3.org/2001/XMLSchema`
- `0x7a2d6`: `XmlInvalidDataTypeUsage`
- `0x7a30f`: `XmlInvalidXsdDataType`
- `0x7a359`: `XmlDataTypeMismatch`
- `0x7a3a7`: `XmlInvalidTypeAttributes`
- `0x7a2e8`: `XmlElementAttribute.DataType`
- `0x7a321`: `XmlElementAttribute.DataType`
- `0x7a36b`: `XmlElementAttribute.DataType`
- `0x7a58a`: `XmlSerializableAttributes`

## pseudocode

```c

```

## disassembly

```asm
0x7a2a0  ldarg.s  4
0x7a2a2  callvirt instance int32 [mscorlib]System.String::get_Length()
0x7a2a7  ldc.i4.0
0x7a2a8  ble      loc_7A385
0x7a2ad  ldarg.1
0x7a2ae  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeModel::get_Type()
0x7a2b3  call     bool System.Xml.Serialization.TypeScope::IsOptionalValue(class [mscorlib]System.Type type)
0x7a2b8  brtrue.s loc_7A2C2
0x7a2ba  ldarg.1
0x7a2bb  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x7a2c0  br.s     loc_7A2CD
0x7a2c2  ldarg.1
0x7a2c3  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x7a2c8  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_BaseTypeDesc()
0x7a2cd  stloc.0
0x7a2ce  ldloc.0
0x7a2cf  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsPrimitive()
0x7a2d4  brtrue.s loc_7A2F9
0x7a2d6  ldstr    aXmlinvaliddata// "XmlInvalidDataTypeUsage"
0x7a2db  ldc.i4.2
0x7a2dc  newarr   [mscorlib]System.Object
0x7a2e1  dup
0x7a2e2  ldc.i4.0
0x7a2e3  ldarg.s  4
0x7a2e5  stelem.ref
0x7a2e6  dup
0x7a2e7  ldc.i4.1
0x7a2e8  ldstr    aXmlelementattr// "XmlElementAttribute.DataType"
0x7a2ed  stelem.ref
0x7a2ee  call     string System.Xml.Res::GetString(string name, object[] args)
0x7a2f3  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7a2f8  throw
0x7a2f9  ldarg.0
0x7a2fa  ldfld    class System.Xml.Serialization.TypeScope System.Xml.Serialization.XmlReflectionImporter::typeScope
0x7a2ff  ldarg.s  4
0x7a301  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x7a306  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeScope::GetTypeDesc(string name, string ns)
0x7a30b  stloc.1
0x7a30c  ldloc.1
0x7a30d  brtrue.s loc_7A346
0x7a30f  ldstr    aXmlinvalidxsdd// "XmlInvalidXsdDataType"
0x7a314  ldc.i4.3
0x7a315  newarr   [mscorlib]System.Object
0x7a31a  dup
0x7a31b  ldc.i4.0
0x7a31c  ldarg.s  4
0x7a31e  stelem.ref
0x7a31f  dup
0x7a320  ldc.i4.1
0x7a321  ldstr    aXmlelementattr// "XmlElementAttribute.DataType"
0x7a326  stelem.ref
0x7a327  dup
0x7a328  ldc.i4.2
0x7a329  ldarg.s  4
0x7a32b  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x7a330  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x7a335  callvirt instance string [mscorlib]System.Object::ToString()
0x7a33a  stelem.ref
0x7a33b  call     string System.Xml.Res::GetString(string name, object[] args)
0x7a340  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7a345  throw
0x7a346  ldloc.0
0x7a347  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x7a34c  ldloc.1
0x7a34d  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x7a352  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x7a357  brfalse.s loc_7A385
0x7a359  ldstr    aXmldatatypemis// "XmlDataTypeMismatch"
0x7a35e  ldc.i4.3
0x7a35f  newarr   [mscorlib]System.Object
0x7a364  dup
0x7a365  ldc.i4.0
0x7a366  ldarg.s  4
0x7a368  stelem.ref
0x7a369  dup
0x7a36a  ldc.i4.1
0x7a36b  ldstr    aXmlelementattr// "XmlElementAttribute.DataType"
0x7a370  stelem.ref
0x7a371  dup
0x7a372  ldc.i4.2
0x7a373  ldloc.0
0x7a374  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x7a379  stelem.ref
0x7a37a  call     string System.Xml.Res::GetString(string name, object[] args)
0x7a37f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7a384  throw
0x7a385  ldarg.s  5
0x7a387  brtrue.s loc_7A398
0x7a389  ldarg.0
0x7a38a  ldarg.1
0x7a38b  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeModel::get_Type()
0x7a390  ldc.i4.0
0x7a391  call     instance class System.Xml.Serialization.XmlAttributes System.Xml.Serialization.XmlReflectionImporter::GetAttributes(class [mscorlib]System.Type type, bool canBeSimpleType)
0x7a396  starg.s  5
0x7a398  ldarg.s  5
0x7a39a  callvirt instance valuetype System.Xml.Serialization.XmlAttributeFlags System.Xml.Serialization.XmlAttributes::get_XmlFlags()
0x7a39f  ldc.i4   0xFFFFFF3F
0x7a3a4  and
0x7a3a5  brfalse.s loc_7A3CB
0x7a3a7  ldstr    aXmlinvalidtype// "XmlInvalidTypeAttributes"
0x7a3ac  ldc.i4.1
0x7a3ad  newarr   [mscorlib]System.Object
0x7a3b2  dup
0x7a3b3  ldc.i4.0
0x7a3b4  ldarg.1
0x7a3b5  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeModel::get_Type()
0x7a3ba  callvirt instance string [mscorlib]System.Type::get_FullName()
0x7a3bf  stelem.ref
0x7a3c0  call     string System.Xml.Res::GetString(string name, object[] args)
0x7a3c5  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7a3ca  throw
0x7a3cb  ldarg.1
0x7a3cc  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x7a3d1  callvirt instance valuetype System.Xml.Serialization.TypeKind System.Xml.Serialization.TypeDesc::get_Kind()
0x7a3d6  stloc.3
0x7a3d7  ldloc.3
0x7a3d8  switch   loc_7A48A, loc_7A418, loc_7A402, loc_7A48A, loc_7A48A, loc_7A445, loc_7A445, loc_7A445
0x7a3fd  br       loc_7A56F
0x7a402  ldarg.0
0x7a403  ldarg.1
0x7a404  castclass System.Xml.Serialization.EnumModel
0x7a409  ldarg.2
0x7a40a  ldarg.s  6
0x7a40c  call     instance class System.Xml.Serialization.EnumMapping System.Xml.Serialization.XmlReflectionImporter::ImportEnumMapping(class System.Xml.Serialization.EnumModel model, string ns, bool repeats)
0x7a411  stloc.s  4
0x7a413  leave    loc_7A63C
0x7a418  ldarg.s  5
0x7a41a  callvirt instance valuetype System.Xml.Serialization.XmlAttributeFlags System.Xml.Serialization.XmlAttributes::get_XmlFlags()
0x7a41f  brfalse.s loc_7A42D
0x7a421  ldarg.1
0x7a422  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeModel::get_Type()
0x7a427  call     class [mscorlib]System.Exception System.Xml.Serialization.XmlReflectionImporter::InvalidAttributeUseException(class [mscorlib]System.Type type)
0x7a42c  throw
0x7a42d  ldarg.0
0x7a42e  ldarg.1
0x7a42f  castclass System.Xml.Serialization.PrimitiveModel
0x7a434  ldarg.3
0x7a435  ldarg.s  4
0x7a437  ldarg.s  6
0x7a439  call     instance class System.Xml.Serialization.PrimitiveMapping System.Xml.Serialization.XmlReflectionImporter::ImportPrimitiveMapping(class System.Xml.Serialization.PrimitiveModel model, valuetype ImportContext context, string dataType, bool repeats)
0x7a43e  stloc.s  4
0x7a440  leave    loc_7A63C
0x7a445  ldarg.3
0x7a446  ldc.i4.2
0x7a447  beq.s    loc_7A456
0x7a449  ldarg.1
0x7a44a  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x7a44f  ldarg.3
0x7a450  call     class [mscorlib]System.Exception System.Xml.Serialization.XmlReflectionImporter::UnsupportedException(class System.Xml.Serialization.TypeDesc typeDesc, valuetype ImportContext context)
0x7a455  throw
0x7a456  ldarg.0
0x7a457  ldarg.0
0x7a458  ldfld    int32 System.Xml.Serialization.XmlReflectionImporter::arrayNestingLevel
0x7a45d  ldc.i4.1
0x7a45e  add
0x7a45f  stfld    int32 System.Xml.Serialization.XmlReflectionImporter::arrayNestingLevel
0x7a464  ldarg.0
0x7a465  ldarg.1
0x7a466  castclass System.Xml.Serialization.ArrayModel
0x7a46b  ldarg.2
0x7a46c  ldarg.s  8
0x7a46e  call     instance class System.Xml.Serialization.ArrayMapping System.Xml.Serialization.XmlReflectionImporter::ImportArrayLikeMapping(class System.Xml.Serialization.ArrayModel model, string ns, class System.Xml.Serialization.RecursionLimiter limiter)
0x7a473  stloc.2
0x7a474  ldarg.0
0x7a475  ldarg.0
0x7a476  ldfld    int32 System.Xml.Serialization.XmlReflectionImporter::arrayNestingLevel
0x7a47b  ldc.i4.1
0x7a47c  sub
0x7a47d  stfld    int32 System.Xml.Serialization.XmlReflectionImporter::arrayNestingLevel
0x7a482  ldloc.2
0x7a483  stloc.s  4
0x7a485  leave    loc_7A63C
0x7a48a  ldarg.3
0x7a48b  ldc.i4.2
0x7a48c  beq.s    loc_7A49B
0x7a48e  ldarg.1
0x7a48f  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x7a494  ldarg.3
0x7a495  call     class [mscorlib]System.Exception System.Xml.Serialization.XmlReflectionImporter::UnsupportedException(class System.Xml.Serialization.TypeDesc typeDesc, valuetype ImportContext context)
0x7a49a  throw
0x7a49b  ldarg.1
0x7a49c  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x7a4a1  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsOptionalValue()
0x7a4a6  brfalse  loc_7A555
0x7a4ab  ldarg.s  4
0x7a4ad  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7a4b2  brtrue.s loc_7A4C8
0x7a4b4  ldarg.0
0x7a4b5  ldfld    class System.Xml.Serialization.TypeScope System.Xml.Serialization.XmlReflectionImporter::typeScope
0x7a4ba  ldarg.s  4
0x7a4bc  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x7a4c1  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeScope::GetTypeDesc(string name, string ns)
0x7a4c6  br.s     loc_7A4D3
0x7a4c8  ldarg.1
0x7a4c9  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x7a4ce  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_BaseTypeDesc()
0x7a4d3  stloc.s  5
0x7a4d5  ldloc.s  5
0x7a4d7  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.TypeDesc::get_DataType()
0x7a4dc  brfalse.s loc_7A4EC
0x7a4de  ldloc.s  5
0x7a4e0  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.TypeDesc::get_DataType()
0x7a4e5  callvirt instance string System.Xml.Schema.XmlSchemaType::get_Name()
0x7a4ea  br.s     loc_7A4F3
0x7a4ec  ldloc.s  5
0x7a4ee  callvirt instance string System.Xml.Serialization.TypeDesc::get_Name()
0x7a4f3  stloc.s  6
0x7a4f5  ldarg.0
0x7a4f6  ldloc.s  6
0x7a4f8  ldarg.2
0x7a4f9  ldloc.s  5
0x7a4fb  ldarg.0
0x7a4fc  ldfld    class System.Xml.Serialization.NameTable System.Xml.Serialization.XmlReflectionImporter::types
0x7a501  ldnull
0x7a502  call     instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.XmlReflectionImporter::GetTypeMapping(string typeName, string ns, class System.Xml.Serialization.TypeDesc typeDesc, class System.Xml.Serialization.NameTable typeLib, class [mscorlib]System.Type type)
0x7a507  stloc.s  7
0x7a509  ldloc.s  7
0x7a50b  brtrue.s loc_7A53B
0x7a50d  ldarg.0
0x7a50e  ldarg.0
0x7a50f  ldfld    class System.Xml.Serialization.ModelScope System.Xml.Serialization.XmlReflectionImporter::modelScope
0x7a514  ldarg.1
0x7a515  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x7a51a  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_BaseTypeDesc()
0x7a51f  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x7a524  callvirt instance class System.Xml.Serialization.TypeModel System.Xml.Serialization.ModelScope::GetTypeModel(class [mscorlib]System.Type type)
0x7a529  ldarg.2
0x7a52a  ldarg.3
0x7a52b  ldarg.s  4
0x7a52d  ldnull
0x7a52e  ldarg.s  6
0x7a530  ldarg.s  7
0x7a532  ldarg.s  8
0x7a534  call     instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.XmlReflectionImporter::ImportTypeMapping(class System.Xml.Serialization.TypeModel model, string ns, valuetype ImportContext context, string dataType, class System.Xml.Serialization.XmlAttributes a, bool repeats, bool openModel, class System.Xml.Serialization.RecursionLimiter limiter)
0x7a539  stloc.s  7
0x7a53b  ldarg.0
0x7a53c  ldloc.s  7
0x7a53e  ldarg.1
0x7a53f  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x7a544  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x7a549  call     instance class System.Xml.Serialization.NullableMapping System.Xml.Serialization.XmlReflectionImporter::CreateNullableMapping(class System.Xml.Serialization.TypeMapping baseMapping, class [mscorlib]System.Type type)
0x7a54e  stloc.s  4
0x7a550  leave    loc_7A63C
0x7a555  ldarg.0
0x7a556  ldarg.1
0x7a557  castclass System.Xml.Serialization.StructModel
0x7a55c  ldarg.2
0x7a55d  ldarg.s  7
0x7a55f  ldarg.s  5
0x7a561  ldarg.s  8
0x7a563  call     instance class System.Xml.Serialization.StructMapping System.Xml.Serialization.XmlReflectionImporter::ImportStructLikeMapping(class System.Xml.Serialization.StructModel model, string ns, bool openModel, class System.Xml.Serialization.XmlAttributes a, class System.Xml.Serialization.RecursionLimiter limiter)
0x7a568  stloc.s  4
0x7a56a  leave    loc_7A63C
0x7a56f  ldarg.1
0x7a570  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x7a575  callvirt instance valuetype System.Xml.Serialization.TypeKind System.Xml.Serialization.TypeDesc::get_Kind()
0x7a57a  ldc.i4.s 0xB
0x7a57c  bne.un.s loc_7A5C0
0x7a57e  ldarg.s  5
0x7a580  callvirt instance valuetype System.Xml.Serialization.XmlAttributeFlags System.Xml.Serialization.XmlAttributes::get_XmlFlags()
0x7a585  ldc.i4.s 0xBF
0x7a587  and
0x7a588  brfalse.s loc_7A5D5
0x7a58a  ldstr    aXmlserializabl_2// "XmlSerializableAttributes"
0x7a58f  ldc.i4.2
0x7a590  newarr   [mscorlib]System.Object
0x7a595  dup
0x7a596  ldc.i4.0
0x7a597  ldarg.1
0x7a598  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x7a59d  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x7a5a2  stelem.ref
0x7a5a3  dup
0x7a5a4  ldc.i4.1
0x7a5a5  ldtoken  System.Xml.Serialization.XmlSchemaProviderAttribute
0x7a5aa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7a5af  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7a5b4  stelem.ref
0x7a5b5  call     string System.Xml.Res::GetString(string name, object[] args)
0x7a5ba  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7a5bf  throw
0x7a5c0  ldarg.s  5
0x7a5c2  callvirt instance valuetype System.Xml.Serialization.XmlAttributeFlags System.Xml.Serialization.XmlAttributes::get_XmlFlags()
0x7a5c7  brfalse.s loc_7A5D5
0x7a5c9  ldarg.1
0x7a5ca  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeModel::get_Type()
0x7a5cf  call     class [mscorlib]System.Exception System.Xml.Serialization.XmlReflectionImporter::InvalidAttributeUseException(class [mscorlib]System.Type type)
0x7a5d4  throw
0x7a5d5  ldarg.1
0x7a5d6  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x7a5db  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsSpecial()
0x7a5e0  brfalse.s loc_7A5FC
0x7a5e2  ldarg.0
0x7a5e3  ldarg.1
0x7a5e4  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeModel::get_Type()
0x7a5e9  ldarg.1
0x7a5ea  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x7a5ef  ldarg.2
0x7a5f0  ldarg.3
0x7a5f1  ldarg.s  8
  ... truncated ...
```
