# System.Xml.Serialization.XmlSchemaImporter::FindDataType

- ea: `0x84660`
- end: `0x8477c`
- name: `System.Xml.Serialization.XmlSchemaImporter::FindDataType`
- size: `284`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x83f50`
- `0x845e0`
- `0x84780`

## callees

- `0x13310`
- `0x13320`
- `0x13380`
- `0x13410`
- `0x622f0`
- `0x6b360`
- `0x6b380`
- `0x72be0`
- `0x73d40`
- `0x73d90`
- `0x84660`
- `0x84f40`

## string_xrefs

- `0x846ed`: `http://www.w3.org/2001/XMLSchema`
- `0x84704`: `http://www.w3.org/2001/XMLSchema`
- `0x84732`: `http://schemas.xmlsoap.org/soap/encoding/`
- `0x8475d`: `XmlMissingDataType`
- `0x8473e`: `XmlInvalidEncoding`

## pseudocode

```c

```

## disassembly

```asm
0x84660  ldarg.1
0x84661  ldnull
0x84662  call     bool System.Xml.XmlQualifiedName::op_Equality(class System.Xml.XmlQualifiedName a, class System.Xml.XmlQualifiedName b)
0x84667  brtrue.s loc_84671
0x84669  ldarg.1
0x8466a  callvirt instance bool System.Xml.XmlQualifiedName::get_IsEmpty()
0x8466f  brfalse.s loc_84691
0x84671  ldarg.0
0x84672  call     instance class System.Xml.Serialization.TypeScope System.Xml.Serialization.SchemaImporter::get_Scope()
0x84677  ldtoken  [mscorlib]System.String
0x8467c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x84681  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeScope::GetTypeDesc(class [mscorlib]System.Type type)
0x84686  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.TypeDesc::get_DataType()
0x8468b  castclass System.Xml.Schema.XmlSchemaSimpleType
0x84690  ret
0x84691  ldarg.0
0x84692  call     instance class System.Xml.Serialization.TypeScope System.Xml.Serialization.SchemaImporter::get_Scope()
0x84697  ldarg.1
0x84698  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x8469d  ldarg.1
0x8469e  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x846a3  ldarg.2
0x846a4  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeScope::GetTypeDesc(string name, string ns, valuetype System.Xml.Serialization.TypeFlags flags)
0x846a9  stloc.0
0x846aa  ldloc.0
0x846ab  brfalse.s loc_846C6
0x846ad  ldloc.0
0x846ae  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.TypeDesc::get_DataType()
0x846b3  isinst   System.Xml.Schema.XmlSchemaSimpleType
0x846b8  brfalse.s loc_846C6
0x846ba  ldloc.0
0x846bb  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.TypeDesc::get_DataType()
0x846c0  castclass System.Xml.Schema.XmlSchemaSimpleType
0x846c5  ret
0x846c6  ldarg.0
0x846c7  call     instance class System.Xml.Serialization.XmlSchemas System.Xml.Serialization.SchemaImporter::get_Schemas()
0x846cc  ldarg.1
0x846cd  ldtoken  System.Xml.Schema.XmlSchemaSimpleType
0x846d2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x846d7  callvirt instance object System.Xml.Serialization.XmlSchemas::Find(class System.Xml.XmlQualifiedName name, class [mscorlib]System.Type type)
0x846dc  castclass System.Xml.Schema.XmlSchemaSimpleType
0x846e1  stloc.1
0x846e2  ldloc.1
0x846e3  brfalse.s loc_846E7
0x846e5  ldloc.1
0x846e6  ret
0x846e7  ldarg.1
0x846e8  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x846ed  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x846f2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x846f7  brfalse.s loc_8471A
0x846f9  ldarg.0
0x846fa  call     instance class System.Xml.Serialization.TypeScope System.Xml.Serialization.SchemaImporter::get_Scope()
0x846ff  ldstr    aString// "string"
0x84704  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x84709  ldarg.2
0x8470a  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeScope::GetTypeDesc(string name, string ns, valuetype System.Xml.Serialization.TypeFlags flags)
0x8470f  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.TypeDesc::get_DataType()
0x84714  castclass System.Xml.Schema.XmlSchemaSimpleType
0x84719  ret
0x8471a  ldarg.1
0x8471b  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x84720  ldstr    aArray_0// "Array"
0x84725  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8472a  brfalse.s loc_8475D
0x8472c  ldarg.1
0x8472d  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x84732  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/encodin"...
0x84737  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8473c  brfalse.s loc_8475D
0x8473e  ldstr    aXmlinvalidenco_1// "XmlInvalidEncoding"
0x84743  ldc.i4.1
0x84744  newarr   [mscorlib]System.Object
0x84749  dup
0x8474a  ldc.i4.0
0x8474b  ldarg.1
0x8474c  callvirt instance string [mscorlib]System.Object::ToString()
0x84751  stelem.ref
0x84752  call     string System.Xml.Res::GetString(string name, object[] args)
0x84757  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8475c  throw
0x8475d  ldstr    aXmlmissingdata// "XmlMissingDataType"
0x84762  ldc.i4.1
0x84763  newarr   [mscorlib]System.Object
0x84768  dup
0x84769  ldc.i4.0
0x8476a  ldarg.1
0x8476b  callvirt instance string [mscorlib]System.Object::ToString()
0x84770  stelem.ref
0x84771  call     string System.Xml.Res::GetString(string name, object[] args)
0x84776  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8477b  throw
```
