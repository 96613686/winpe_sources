# System.Xml.Serialization.XmlSchemaImporter::ImportType

- ea: `0x81a00`
- end: `0x81af3`
- name: `System.Xml.Serialization.XmlSchemaImporter::ImportType`
- size: `243`
- prototype: ``
- caller_count: `8`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x80f30`
- `0x81080`
- `0x81570`
- `0x81910`
- `0x81c50`
- `0x82e30`
- `0x83d70`
- `0x83f50`

## callees

- `0x13310`
- `0x13320`
- `0x62370`
- `0x6b340`
- `0x6b3c0`
- `0x6b520`
- `0x6b560`
- `0x6b5b0`
- `0x81a00`
- `0x81b00`
- `0x83f50`
- `0x84780`

## string_xrefs

- `0x81a18`: `http://www.w3.org/2001/XMLSchema`
- `0x81ad8`: `http://www.w3.org/2001/XMLSchema`
- `0x81abe`: `XmlInternalError`
- `0x81a66`: `XmlCircularTypeReference`

## pseudocode

```c

```

## disassembly

```asm
0x81a00  ldarg.1
0x81a01  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x81a06  ldstr    aAnytype// "anyType"
0x81a0b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x81a10  brfalse.s loc_81A2B
0x81a12  ldarg.1
0x81a13  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x81a18  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x81a1d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x81a22  brfalse.s loc_81A2B
0x81a24  ldarg.0
0x81a25  call     instance class System.Xml.Serialization.StructMapping System.Xml.Serialization.SchemaImporter::ImportRootMapping()
0x81a2a  ret
0x81a2b  ldarg.0
0x81a2c  ldarg.1
0x81a2d  ldarg.s  4
0x81a2f  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.XmlSchemaImporter::FindType(class System.Xml.XmlQualifiedName name, valuetype System.Xml.Serialization.TypeFlags flags)
0x81a34  stloc.0
0x81a35  ldarg.0
0x81a36  call     instance class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.SchemaImporter::get_ImportedMappings()
0x81a3b  ldloc.0
0x81a3c  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x81a41  castclass System.Xml.Serialization.TypeMapping
0x81a46  stloc.1
0x81a47  ldloc.1
0x81a48  brfalse.s loc_81A5A
0x81a4a  ldarg.2
0x81a4b  ldloc.1
0x81a4c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x81a51  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x81a56  brfalse.s loc_81A5A
0x81a58  ldloc.1
0x81a59  ret
0x81a5a  ldarg.s  5
0x81a5c  brfalse.s loc_81A70
0x81a5e  ldarg.0
0x81a5f  ldarg.1
0x81a60  ldarg.0
0x81a61  call     instance class System.Xml.Serialization.NameTable System.Xml.Serialization.SchemaImporter::get_TypesInUse()
0x81a66  ldstr    aXmlcirculartyp// "XmlCircularTypeReference"
0x81a6b  call     instance void System.Xml.Serialization.SchemaImporter::AddReference(class System.Xml.XmlQualifiedName name, class System.Xml.Serialization.NameTable references, string error)
0x81a70  ldloc.0
0x81a71  isinst   System.Xml.Schema.XmlSchemaComplexType
0x81a76  brfalse.s loc_81A97
0x81a78  ldarg.0
0x81a79  ldloc.0
0x81a7a  castclass System.Xml.Schema.XmlSchemaComplexType
0x81a7f  ldarg.1
0x81a80  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x81a85  ldarg.1
0x81a86  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x81a8b  ldarg.2
0x81a8c  ldarg.3
0x81a8d  ldarg.s  4
0x81a8f  call     instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.XmlSchemaImporter::ImportType(class System.Xml.Schema.XmlSchemaComplexType type, string typeNs, string identifier, class [mscorlib]System.Type desiredMappingType, class [mscorlib]System.Type baseType, valuetype System.Xml.Serialization.TypeFlags flags)
0x81a94  stloc.1
0x81a95  br.s     loc_81ACE
0x81a97  ldloc.0
0x81a98  isinst   System.Xml.Schema.XmlSchemaSimpleType
0x81a9d  brfalse.s loc_81ABE
0x81a9f  ldarg.0
0x81aa0  ldloc.0
0x81aa1  castclass System.Xml.Schema.XmlSchemaSimpleType
0x81aa6  ldarg.1
0x81aa7  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x81aac  ldarg.1
0x81aad  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x81ab2  ldarg.3
0x81ab3  ldarg.s  4
0x81ab5  ldc.i4.0
0x81ab6  call     instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.XmlSchemaImporter::ImportDataType(class System.Xml.Schema.XmlSchemaSimpleType dataType, string typeNs, string identifier, class [mscorlib]System.Type baseType, valuetype System.Xml.Serialization.TypeFlags flags, bool isList)
0x81abb  stloc.1
0x81abc  br.s     loc_81ACE
0x81abe  ldstr    aXmlinternalerr// "XmlInternalError"
0x81ac3  call     string System.Xml.Res::GetString(string name)
0x81ac8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x81acd  throw
0x81ace  ldarg.s  5
0x81ad0  brfalse.s loc_81AF1
0x81ad2  ldarg.1
0x81ad3  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x81ad8  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x81add  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x81ae2  brfalse.s loc_81AF1
0x81ae4  ldarg.0
0x81ae5  ldarg.1
0x81ae6  ldarg.0
0x81ae7  call     instance class System.Xml.Serialization.NameTable System.Xml.Serialization.SchemaImporter::get_TypesInUse()
0x81aec  call     instance void System.Xml.Serialization.SchemaImporter::RemoveReference(class System.Xml.XmlQualifiedName name, class System.Xml.Serialization.NameTable references)
0x81af1  ldloc.1
0x81af2  ret
```
