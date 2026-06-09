# System.Xml.Serialization.SerializableMapping::RetrieveSerializableSchema

- ea: `0x6a2d0`
- end: `0x6a655`
- name: `System.Xml.Serialization.SerializableMapping::RetrieveSerializableSchema`
- size: `901`
- prototype: ``
- caller_count: `6`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x69ee0`
- `0x69f30`
- `0x6a050`
- `0x6a060`
- `0x6a070`
- `0x6a0c0`

## callees

- `0x13310`
- `0x13320`
- `0x13380`
- `0x622f0`
- `0x68550`
- `0x6a2d0`
- `0xcba10`
- `0xcfe50`
- `0xcfe90`
- `0xd4230`
- `0xd4760`
- `0xd4850`
- `0xd4f50`
- `0xd5360`
- `0xd6b30`
- `0xd6cd0`

## string_xrefs

- `0x6a475`: `http://www.w3.org/2001/XMLSchema`
- `0x6a3a9`: `XmlGetSchemaEmptyTypeName`
- `0x6a3db`: `XmlGetSchemaMethodReturnType`
- `0x6a4a8`: `XmlMissingSchema`
- `0x6a52a`: `XmlMissingSchema`
- `0x6a4d5`: `XmlGetSchemaInclude`
- `0x6a572`: `XmlGetSchemaTypeMissing`
- `0x6a630`: `XmlSerializableNameMissing1`

## pseudocode

```c

```

## disassembly

```asm
0x6a2d0  ldarg.0
0x6a2d1  ldfld    bool System.Xml.Serialization.SerializableMapping::needSchema
0x6a2d6  brfalse  loc_6A654
0x6a2db  ldarg.0
0x6a2dc  ldc.i4.0
0x6a2dd  stfld    bool System.Xml.Serialization.SerializableMapping::needSchema
0x6a2e2  ldarg.0
0x6a2e3  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Serialization.SerializableMapping::getSchemaMethod
0x6a2e8  ldnull
0x6a2e9  call     bool [mscorlib]System.Reflection.MethodInfo::op_Inequality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x6a2ee  brfalse  loc_6A5EC
0x6a2f3  ldarg.0
0x6a2f4  ldfld    class System.Xml.Schema.XmlSchemaSet System.Xml.Serialization.SerializableMapping::schemas
0x6a2f9  brtrue.s loc_6A306
0x6a2fb  ldarg.0
0x6a2fc  newobj   instance void System.Xml.Schema.XmlSchemaSet::.ctor()
0x6a301  stfld    class System.Xml.Schema.XmlSchemaSet System.Xml.Serialization.SerializableMapping::schemas
0x6a306  ldarg.0
0x6a307  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Serialization.SerializableMapping::getSchemaMethod
0x6a30c  ldnull
0x6a30d  ldc.i4.1
0x6a30e  newarr   [mscorlib]System.Object
0x6a313  dup
0x6a314  ldc.i4.0
0x6a315  ldarg.0
0x6a316  ldfld    class System.Xml.Schema.XmlSchemaSet System.Xml.Serialization.SerializableMapping::schemas
0x6a31b  stelem.ref
0x6a31c  callvirt instance object [mscorlib]System.Reflection.MethodBase::Invoke(object, object[])
0x6a321  stloc.0
0x6a322  ldarg.0
0x6a323  ldsfld   class System.Xml.XmlQualifiedName System.Xml.XmlQualifiedName::Empty
0x6a328  stfld    class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::xsiType
0x6a32d  ldloc.0
0x6a32e  brfalse  loc_6A431
0x6a333  ldtoken  System.Xml.Schema.XmlSchemaType
0x6a338  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6a33d  ldarg.0
0x6a33e  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Serialization.SerializableMapping::getSchemaMethod
0x6a343  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MethodInfo::get_ReturnType()
0x6a348  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x6a34d  brfalse.s loc_6A371
0x6a34f  ldarg.0
0x6a350  ldloc.0
0x6a351  castclass System.Xml.Schema.XmlSchemaType
0x6a356  stfld    class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.SerializableMapping::xsdType
0x6a35b  ldarg.0
0x6a35c  ldarg.0
0x6a35d  ldfld    class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.SerializableMapping::xsdType
0x6a362  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0x6a367  stfld    class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::xsiType
0x6a36c  br       loc_6A438
0x6a371  ldtoken  System.Xml.XmlQualifiedName
0x6a376  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6a37b  ldarg.0
0x6a37c  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Serialization.SerializableMapping::getSchemaMethod
0x6a381  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MethodInfo::get_ReturnType()
0x6a386  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x6a38b  brfalse.s loc_6A3DB
0x6a38d  ldarg.0
0x6a38e  ldloc.0
0x6a38f  castclass System.Xml.XmlQualifiedName
0x6a394  stfld    class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::xsiType
0x6a399  ldarg.0
0x6a39a  ldfld    class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::xsiType
0x6a39f  callvirt instance bool System.Xml.XmlQualifiedName::get_IsEmpty()
0x6a3a4  brfalse  loc_6A438
0x6a3a9  ldstr    aXmlgetschemaem// "XmlGetSchemaEmptyTypeName"
0x6a3ae  ldc.i4.2
0x6a3af  newarr   [mscorlib]System.Object
0x6a3b4  dup
0x6a3b5  ldc.i4.0
0x6a3b6  ldarg.0
0x6a3b7  ldfld    class [mscorlib]System.Type System.Xml.Serialization.SerializableMapping::type
0x6a3bc  callvirt instance string [mscorlib]System.Type::get_FullName()
0x6a3c1  stelem.ref
0x6a3c2  dup
0x6a3c3  ldc.i4.1
0x6a3c4  ldarg.0
0x6a3c5  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Serialization.SerializableMapping::getSchemaMethod
0x6a3ca  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x6a3cf  stelem.ref
0x6a3d0  call     string System.Xml.Res::GetString(string name, object[] args)
0x6a3d5  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6a3da  throw
0x6a3db  ldstr    aXmlgetschemame// "XmlGetSchemaMethodReturnType"
0x6a3e0  ldc.i4.4
0x6a3e1  newarr   [mscorlib]System.Object
0x6a3e6  dup
0x6a3e7  ldc.i4.0
0x6a3e8  ldarg.0
0x6a3e9  ldfld    class [mscorlib]System.Type System.Xml.Serialization.SerializableMapping::type
0x6a3ee  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x6a3f3  stelem.ref
0x6a3f4  dup
0x6a3f5  ldc.i4.1
0x6a3f6  ldarg.0
0x6a3f7  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Serialization.SerializableMapping::getSchemaMethod
0x6a3fc  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x6a401  stelem.ref
0x6a402  dup
0x6a403  ldc.i4.2
0x6a404  ldtoken  System.Xml.Serialization.XmlSchemaProviderAttribute
0x6a409  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6a40e  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x6a413  stelem.ref
0x6a414  dup
0x6a415  ldc.i4.3
0x6a416  ldtoken  System.Xml.XmlQualifiedName
0x6a41b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6a420  callvirt instance string [mscorlib]System.Type::get_FullName()
0x6a425  stelem.ref
0x6a426  call     string System.Xml.Res::GetString(string name, object[] args)
0x6a42b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6a430  throw
0x6a431  ldarg.0
0x6a432  ldc.i4.1
0x6a433  stfld    bool System.Xml.Serialization.SerializableMapping::any
0x6a438  ldarg.0
0x6a439  ldfld    class System.Xml.Schema.XmlSchemaSet System.Xml.Serialization.SerializableMapping::schemas
0x6a43e  ldnull
0x6a43f  ldftn    void System.Xml.Serialization.SerializableMapping::ValidationCallbackWithErrorCode(object sender, class System.Xml.Schema.ValidationEventArgs args)
0x6a445  newobj   instance void System.Xml.Schema.ValidationEventHandler::.ctor(object object, native int method)
0x6a44a  callvirt instance void System.Xml.Schema.XmlSchemaSet::add_ValidationEventHandler(class System.Xml.Schema.ValidationEventHandler value)
0x6a44f  ldarg.0
0x6a450  ldfld    class System.Xml.Schema.XmlSchemaSet System.Xml.Serialization.SerializableMapping::schemas
0x6a455  callvirt instance void System.Xml.Schema.XmlSchemaSet::Compile()
0x6a45a  ldarg.0
0x6a45b  ldfld    class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::xsiType
0x6a460  callvirt instance bool System.Xml.XmlQualifiedName::get_IsEmpty()
0x6a465  brtrue   loc_6A654
0x6a46a  ldarg.0
0x6a46b  ldfld    class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::xsiType
0x6a470  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x6a475  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x6a47a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6a47f  brfalse  loc_6A654
0x6a484  ldarg.0
0x6a485  ldfld    class System.Xml.Schema.XmlSchemaSet System.Xml.Serialization.SerializableMapping::schemas
0x6a48a  ldarg.0
0x6a48b  ldfld    class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::xsiType
0x6a490  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x6a495  callvirt instance class [mscorlib]System.Collections.ICollection System.Xml.Schema.XmlSchemaSet::Schemas(string targetNamespace)
0x6a49a  castclass [mscorlib]System.Collections.ArrayList
0x6a49f  stloc.1
0x6a4a0  ldloc.1
0x6a4a1  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x6a4a6  brtrue.s loc_6A4CC
0x6a4a8  ldstr    aXmlmissingsche// "XmlMissingSchema"
0x6a4ad  ldc.i4.1
0x6a4ae  newarr   [mscorlib]System.Object
0x6a4b3  dup
0x6a4b4  ldc.i4.0
0x6a4b5  ldarg.0
0x6a4b6  ldfld    class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::xsiType
0x6a4bb  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x6a4c0  stelem.ref
0x6a4c1  call     string System.Xml.Res::GetString(string name, object[] args)
0x6a4c6  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6a4cb  throw
0x6a4cc  ldloc.1
0x6a4cd  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x6a4d2  ldc.i4.1
0x6a4d3  ble.s    loc_6A51A
0x6a4d5  ldstr    aXmlgetschemain// "XmlGetSchemaInclude"
0x6a4da  ldc.i4.3
0x6a4db  newarr   [mscorlib]System.Object
0x6a4e0  dup
0x6a4e1  ldc.i4.0
0x6a4e2  ldarg.0
0x6a4e3  ldfld    class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::xsiType
0x6a4e8  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x6a4ed  stelem.ref
0x6a4ee  dup
0x6a4ef  ldc.i4.1
0x6a4f0  ldarg.0
0x6a4f1  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Serialization.SerializableMapping::getSchemaMethod
0x6a4f6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MemberInfo::get_DeclaringType()
0x6a4fb  callvirt instance string [mscorlib]System.Type::get_FullName()
0x6a500  stelem.ref
0x6a501  dup
0x6a502  ldc.i4.2
0x6a503  ldarg.0
0x6a504  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Serialization.SerializableMapping::getSchemaMethod
0x6a509  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x6a50e  stelem.ref
0x6a50f  call     string System.Xml.Res::GetString(string name, object[] args)
0x6a514  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6a519  throw
0x6a51a  ldloc.1
0x6a51b  ldc.i4.0
0x6a51c  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x6a521  castclass System.Xml.Schema.XmlSchema
0x6a526  stloc.2
0x6a527  ldloc.2
0x6a528  brtrue.s loc_6A54E
0x6a52a  ldstr    aXmlmissingsche// "XmlMissingSchema"
0x6a52f  ldc.i4.1
0x6a530  newarr   [mscorlib]System.Object
0x6a535  dup
0x6a536  ldc.i4.0
0x6a537  ldarg.0
0x6a538  ldfld    class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::xsiType
0x6a53d  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x6a542  stelem.ref
0x6a543  call     string System.Xml.Res::GetString(string name, object[] args)
0x6a548  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6a54d  throw
0x6a54e  ldarg.0
0x6a54f  ldloc.2
0x6a550  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchema::get_SchemaTypes()
0x6a555  ldarg.0
0x6a556  ldfld    class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::xsiType
0x6a55b  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0x6a560  castclass System.Xml.Schema.XmlSchemaType
0x6a565  stfld    class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.SerializableMapping::xsdType
0x6a56a  ldarg.0
0x6a56b  ldfld    class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.SerializableMapping::xsdType
0x6a570  brtrue.s loc_6A5C5
0x6a572  ldstr    aXmlgetschematy// "XmlGetSchemaTypeMissing"
0x6a577  ldc.i4.4
0x6a578  newarr   [mscorlib]System.Object
0x6a57d  dup
0x6a57e  ldc.i4.0
0x6a57f  ldarg.0
0x6a580  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Serialization.SerializableMapping::getSchemaMethod
0x6a585  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MemberInfo::get_DeclaringType()
0x6a58a  callvirt instance string [mscorlib]System.Type::get_FullName()
0x6a58f  stelem.ref
0x6a590  dup
0x6a591  ldc.i4.1
0x6a592  ldarg.0
0x6a593  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Serialization.SerializableMapping::getSchemaMethod
0x6a598  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x6a59d  stelem.ref
0x6a59e  dup
0x6a59f  ldc.i4.2
0x6a5a0  ldarg.0
0x6a5a1  ldfld    class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::xsiType
0x6a5a6  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x6a5ab  stelem.ref
0x6a5ac  dup
0x6a5ad  ldc.i4.3
0x6a5ae  ldarg.0
0x6a5af  ldfld    class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::xsiType
0x6a5b4  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x6a5b9  stelem.ref
0x6a5ba  call     string System.Xml.Res::GetString(string name, object[] args)
0x6a5bf  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6a5c4  throw
0x6a5c5  ldarg.0
0x6a5c6  ldarg.0
0x6a5c7  ldfld    class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.SerializableMapping::xsdType
0x6a5cc  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Schema.XmlSchemaType::get_Redefined()
0x6a5d1  brtrue.s loc_6A5DB
0x6a5d3  ldarg.0
0x6a5d4  ldfld    class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.SerializableMapping::xsdType
0x6a5d9  br.s     loc_6A5E6
0x6a5db  ldarg.0
0x6a5dc  ldfld    class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.SerializableMapping::xsdType
0x6a5e1  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Schema.XmlSchemaType::get_Redefined()
0x6a5e6  stfld    class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.SerializableMapping::xsdType
0x6a5eb  ret
0x6a5ec  ldarg.0
0x6a5ed  ldfld    class [mscorlib]System.Type System.Xml.Serialization.SerializableMapping::type
0x6a5f2  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x6a5f7  castclass System.Xml.Serialization.IXmlSerializable
0x6a5fc  stloc.3
0x6a5fd  ldarg.0
0x6a5fe  ldloc.3
0x6a5ff  callvirt instance class System.Xml.Schema.XmlSchema System.Xml.Serialization.IXmlSerializable::GetSchema()
0x6a604  stfld    class System.Xml.Schema.XmlSchema System.Xml.Serialization.SerializableMapping::schema
0x6a609  ldarg.0
0x6a60a  ldfld    class System.Xml.Schema.XmlSchema System.Xml.Serialization.SerializableMapping::schema
0x6a60f  brfalse.s loc_6A654
0x6a611  ldarg.0
0x6a612  ldfld    class System.Xml.Schema.XmlSchema System.Xml.Serialization.SerializableMapping::schema
0x6a617  callvirt instance string System.Xml.Schema.XmlSchema::get_Id()
0x6a61c  brfalse.s loc_6A630
0x6a61e  ldarg.0
0x6a61f  ldfld    class System.Xml.Schema.XmlSchema System.Xml.Serialization.SerializableMapping::schema
0x6a624  callvirt instance string System.Xml.Schema.XmlSchema::get_Id()
0x6a629  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6a62e  brtrue.s loc_6A654
0x6a630  ldstr    aXmlserializabl_1// "XmlSerializableNameMissing1"
0x6a635  ldc.i4.1
0x6a636  newarr   [mscorlib]System.Object
0x6a63b  dup
0x6a63c  ldc.i4.0
0x6a63d  ldarg.0
0x6a63e  ldfld    class [mscorlib]System.Type System.Xml.Serialization.SerializableMapping::type
0x6a643  callvirt instance string [mscorlib]System.Type::get_FullName()
0x6a648  stelem.ref
0x6a649  call     string System.Xml.Res::GetString(string name, object[] args)
0x6a64e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6a653  throw
0x6a654  ret
```
