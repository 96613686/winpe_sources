# System.Xml.Serialization.SoapReflectionImporter::ImportTypeMapping_2

- ea: `0x6ebb0`
- end: `0x6ee28`
- name: `System.Xml.Serialization.SoapReflectionImporter::ImportTypeMapping_2`
- size: `632`
- prototype: ``
- caller_count: `3`
- callee_count: `24`
- tags: `registry_config`

## callers

- `0x6eba0`
- `0x6ebb0`
- `0x6fbb0`

## callees

- `0x132e0`
- `0x622f0`
- `0x6a6b0`
- `0x6a800`
- `0x6a820`
- `0x6de70`
- `0x6deb0`
- `0x6eb50`
- `0x6ebb0`
- `0x6eec0`
- `0x6ef20`
- `0x6f060`
- `0x6f420`
- `0x6f6e0`
- `0x6f7a0`
- `0x72350`
- `0x72b80`
- `0x72b90`
- `0x72bf0`
- `0x72c10`
- `0x72d70`
- `0x72e20`
- `0x730b0`
- `0x73d30`

## string_xrefs

- `0x6ebf2`: `http://www.w3.org/2001/XMLSchema`
- `0x6ec1a`: `http://www.w3.org/2001/XMLSchema`
- `0x6ed7f`: `http://www.w3.org/2001/XMLSchema`
- `0x6ebc9`: `XmlInvalidDataTypeUsage`
- `0x6ec00`: `XmlInvalidXsdDataType`
- `0x6ec4d`: `XmlDataTypeMismatch`
- `0x6ec95`: `XmlInvalidTypeAttributes`
- `0x6ee04`: `XmlUnsupportedSoapTypeKind`

## pseudocode

```c

```

## disassembly

```asm
0x6ebb0  ldarg.2
0x6ebb1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6ebb6  ldc.i4.0
0x6ebb7  ble      loc_6EC7D
0x6ebbc  ldarg.1
0x6ebbd  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x6ebc2  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsPrimitive()
0x6ebc7  brtrue.s loc_6EBEB
0x6ebc9  ldstr    aXmlinvaliddata// "XmlInvalidDataTypeUsage"
0x6ebce  ldc.i4.2
0x6ebcf  newarr   [mscorlib]System.Object
0x6ebd4  dup
0x6ebd5  ldc.i4.0
0x6ebd6  ldarg.2
0x6ebd7  stelem.ref
0x6ebd8  dup
0x6ebd9  ldc.i4.1
0x6ebda  ldstr    aSoapelementatt// "SoapElementAttribute.DataType"
0x6ebdf  stelem.ref
0x6ebe0  call     string System.Xml.Res::GetString(string name, object[] args)
0x6ebe5  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6ebea  throw
0x6ebeb  ldarg.0
0x6ebec  ldfld    class System.Xml.Serialization.TypeScope System.Xml.Serialization.SoapReflectionImporter::typeScope
0x6ebf1  ldarg.2
0x6ebf2  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x6ebf7  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeScope::GetTypeDesc(string name, string ns)
0x6ebfc  stloc.1
0x6ebfd  ldloc.1
0x6ebfe  brtrue.s loc_6EC35
0x6ec00  ldstr    aXmlinvalidxsdd// "XmlInvalidXsdDataType"
0x6ec05  ldc.i4.3
0x6ec06  newarr   [mscorlib]System.Object
0x6ec0b  dup
0x6ec0c  ldc.i4.0
0x6ec0d  ldarg.2
0x6ec0e  stelem.ref
0x6ec0f  dup
0x6ec10  ldc.i4.1
0x6ec11  ldstr    aSoapelementatt// "SoapElementAttribute.DataType"
0x6ec16  stelem.ref
0x6ec17  dup
0x6ec18  ldc.i4.2
0x6ec19  ldarg.2
0x6ec1a  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x6ec1f  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x6ec24  callvirt instance string [mscorlib]System.Object::ToString()
0x6ec29  stelem.ref
0x6ec2a  call     string System.Xml.Res::GetString(string name, object[] args)
0x6ec2f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6ec34  throw
0x6ec35  ldarg.1
0x6ec36  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x6ec3b  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x6ec40  ldloc.1
0x6ec41  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x6ec46  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6ec4b  brfalse.s loc_6EC7D
0x6ec4d  ldstr    aXmldatatypemis// "XmlDataTypeMismatch"
0x6ec52  ldc.i4.3
0x6ec53  newarr   [mscorlib]System.Object
0x6ec58  dup
0x6ec59  ldc.i4.0
0x6ec5a  ldarg.2
0x6ec5b  stelem.ref
0x6ec5c  dup
0x6ec5d  ldc.i4.1
0x6ec5e  ldstr    aSoapelementatt// "SoapElementAttribute.DataType"
0x6ec63  stelem.ref
0x6ec64  dup
0x6ec65  ldc.i4.2
0x6ec66  ldarg.1
0x6ec67  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x6ec6c  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x6ec71  stelem.ref
0x6ec72  call     string System.Xml.Res::GetString(string name, object[] args)
0x6ec77  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6ec7c  throw
0x6ec7d  ldarg.0
0x6ec7e  ldarg.1
0x6ec7f  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeModel::get_Type()
0x6ec84  call     instance class System.Xml.Serialization.SoapAttributes System.Xml.Serialization.SoapReflectionImporter::GetAttributes(class [mscorlib]System.Type type)
0x6ec89  stloc.0
0x6ec8a  ldloc.0
0x6ec8b  callvirt instance valuetype System.Xml.Serialization.SoapAttributeFlags System.Xml.Serialization.SoapAttributes::get_SoapFlags()
0x6ec90  ldc.i4.s 0xFD
0x6ec92  and
0x6ec93  brfalse.s loc_6ECB9
0x6ec95  ldstr    aXmlinvalidtype// "XmlInvalidTypeAttributes"
0x6ec9a  ldc.i4.1
0x6ec9b  newarr   [mscorlib]System.Object
0x6eca0  dup
0x6eca1  ldc.i4.0
0x6eca2  ldarg.1
0x6eca3  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeModel::get_Type()
0x6eca8  callvirt instance string [mscorlib]System.Type::get_FullName()
0x6ecad  stelem.ref
0x6ecae  call     string System.Xml.Res::GetString(string name, object[] args)
0x6ecb3  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6ecb8  throw
0x6ecb9  ldarg.1
0x6ecba  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x6ecbf  callvirt instance valuetype System.Xml.Serialization.TypeKind System.Xml.Serialization.TypeDesc::get_Kind()
0x6ecc4  stloc.2
0x6ecc5  ldloc.2
0x6ecc6  switch   loc_6ED19, loc_6ECFD, loc_6ECF0, loc_6ED19, loc_6ED19, loc_6ED0B, loc_6ED0B, loc_6ED0B
0x6eceb  br       loc_6EE04
0x6ecf0  ldarg.0
0x6ecf1  ldarg.1
0x6ecf2  castclass System.Xml.Serialization.EnumModel
0x6ecf7  call     instance class System.Xml.Serialization.EnumMapping System.Xml.Serialization.SoapReflectionImporter::ImportEnumMapping(class System.Xml.Serialization.EnumModel model)
0x6ecfc  ret
0x6ecfd  ldarg.0
0x6ecfe  ldarg.1
0x6ecff  castclass System.Xml.Serialization.PrimitiveModel
0x6ed04  ldarg.2
0x6ed05  call     instance class System.Xml.Serialization.PrimitiveMapping System.Xml.Serialization.SoapReflectionImporter::ImportPrimitiveMapping(class System.Xml.Serialization.PrimitiveModel model, string dataType)
0x6ed0a  ret
0x6ed0b  ldarg.0
0x6ed0c  ldarg.1
0x6ed0d  castclass System.Xml.Serialization.ArrayModel
0x6ed12  ldarg.3
0x6ed13  call     instance class System.Xml.Serialization.ArrayMapping System.Xml.Serialization.SoapReflectionImporter::ImportArrayLikeMapping(class System.Xml.Serialization.ArrayModel model, class System.Xml.Serialization.RecursionLimiter limiter)
0x6ed18  ret
0x6ed19  ldarg.1
0x6ed1a  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x6ed1f  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsOptionalValue()
0x6ed24  brfalse  loc_6EDF6
0x6ed29  ldarg.1
0x6ed2a  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x6ed2f  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_BaseTypeDesc()
0x6ed34  stloc.3
0x6ed35  ldarg.0
0x6ed36  ldloc.3
0x6ed37  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x6ed3c  call     instance class System.Xml.Serialization.SoapAttributes System.Xml.Serialization.SoapReflectionImporter::GetAttributes(class [mscorlib]System.Type type)
0x6ed41  stloc.s  4
0x6ed43  ldarg.0
0x6ed44  ldfld    string System.Xml.Serialization.SoapReflectionImporter::defaultNs
0x6ed49  stloc.s  5
0x6ed4b  ldloc.s  4
0x6ed4d  callvirt instance class System.Xml.Serialization.SoapTypeAttribute System.Xml.Serialization.SoapAttributes::get_SoapType()
0x6ed52  brfalse.s loc_6ED70
0x6ed54  ldloc.s  4
0x6ed56  callvirt instance class System.Xml.Serialization.SoapTypeAttribute System.Xml.Serialization.SoapAttributes::get_SoapType()
0x6ed5b  callvirt instance string System.Xml.Serialization.SoapTypeAttribute::get_Namespace()
0x6ed60  brfalse.s loc_6ED70
0x6ed62  ldloc.s  4
0x6ed64  callvirt instance class System.Xml.Serialization.SoapTypeAttribute System.Xml.Serialization.SoapAttributes::get_SoapType()
0x6ed69  callvirt instance string System.Xml.Serialization.SoapTypeAttribute::get_Namespace()
0x6ed6e  stloc.s  5
0x6ed70  ldarg.2
0x6ed71  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6ed76  brtrue.s loc_6ED8B
0x6ed78  ldarg.0
0x6ed79  ldfld    class System.Xml.Serialization.TypeScope System.Xml.Serialization.SoapReflectionImporter::typeScope
0x6ed7e  ldarg.2
0x6ed7f  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x6ed84  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeScope::GetTypeDesc(string name, string ns)
0x6ed89  br.s     loc_6ED96
0x6ed8b  ldarg.1
0x6ed8c  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x6ed91  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_BaseTypeDesc()
0x6ed96  stloc.s  6
0x6ed98  ldarg.2
0x6ed99  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6ed9e  brtrue.s loc_6EDA3
0x6eda0  ldarg.2
0x6eda1  br.s     loc_6EDB3
0x6eda3  ldarg.1
0x6eda4  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x6eda9  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeDesc::get_BaseTypeDesc()
0x6edae  callvirt instance string System.Xml.Serialization.TypeDesc::get_Name()
0x6edb3  stloc.s  7
0x6edb5  ldarg.0
0x6edb6  ldloc.s  7
0x6edb8  ldloc.s  5
0x6edba  ldloc.s  6
0x6edbc  call     instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.SoapReflectionImporter::GetTypeMapping(string typeName, string ns, class System.Xml.Serialization.TypeDesc typeDesc)
0x6edc1  stloc.s  8
0x6edc3  ldloc.s  8
0x6edc5  brtrue.s loc_6EDE2
0x6edc7  ldarg.0
0x6edc8  ldarg.0
0x6edc9  ldfld    class System.Xml.Serialization.ModelScope System.Xml.Serialization.SoapReflectionImporter::modelScope
0x6edce  ldloc.3
0x6edcf  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x6edd4  callvirt instance class System.Xml.Serialization.TypeModel System.Xml.Serialization.ModelScope::GetTypeModel(class [mscorlib]System.Type type)
0x6edd9  ldarg.2
0x6edda  ldarg.3
0x6eddb  call     instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.SoapReflectionImporter::ImportTypeMapping(class System.Xml.Serialization.TypeModel model, string dataType, class System.Xml.Serialization.RecursionLimiter limiter)
0x6ede0  stloc.s  8
0x6ede2  ldarg.0
0x6ede3  ldloc.s  8
0x6ede5  ldarg.1
0x6ede6  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x6edeb  callvirt instance class [mscorlib]System.Type System.Xml.Serialization.TypeDesc::get_Type()
0x6edf0  call     instance class System.Xml.Serialization.NullableMapping System.Xml.Serialization.SoapReflectionImporter::CreateNullableMapping(class System.Xml.Serialization.TypeMapping baseMapping, class [mscorlib]System.Type type)
0x6edf5  ret
0x6edf6  ldarg.0
0x6edf7  ldarg.1
0x6edf8  castclass System.Xml.Serialization.StructModel
0x6edfd  ldarg.3
0x6edfe  call     instance class System.Xml.Serialization.StructMapping System.Xml.Serialization.SoapReflectionImporter::ImportStructLikeMapping(class System.Xml.Serialization.StructModel model, class System.Xml.Serialization.RecursionLimiter limiter)
0x6ee03  ret
0x6ee04  ldstr    aXmlunsupported_0// "XmlUnsupportedSoapTypeKind"
0x6ee09  ldc.i4.1
0x6ee0a  newarr   [mscorlib]System.Object
0x6ee0f  dup
0x6ee10  ldc.i4.0
0x6ee11  ldarg.1
0x6ee12  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeModel::get_TypeDesc()
0x6ee17  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x6ee1c  stelem.ref
0x6ee1d  call     string System.Xml.Res::GetString(string name, object[] args)
0x6ee22  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x6ee27  throw
```
