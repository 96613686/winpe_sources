# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write5_ReferencedCollectionType

- ea: `0x6c10`
- end: `0x6c9e`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write5_ReferencedCollectionType`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6690`

## callees

- `0x3150`
- `0x3170`
- `0x6c10`
- `0x6ca0`

## string_xrefs

- `0x6c5a`: `urn:schemas-microsoft-com:xml-wcfservicemap`

## pseudocode

```c

```

## disassembly

```asm
0x6c10  ldarg.3
0x6c11  brtrue.s loc_6C20
0x6c13  ldarg.s  4
0x6c15  brfalse.s loc_6C1F
0x6c17  ldarg.0
0x6c18  ldarg.1
0x6c19  ldarg.2
0x6c1a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x6c1f  ret
0x6c20  ldarg.s  5
0x6c22  brtrue.s loc_6C45
0x6c24  ldarg.3
0x6c25  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6c2a  stloc.0
0x6c2b  ldloc.0
0x6c2c  ldtoken  System.Web.Compilation.WCFModel.ReferencedCollectionType
0x6c31  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6c36  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6c3b  brtrue.s loc_6C45
0x6c3d  ldarg.0
0x6c3e  ldarg.3
0x6c3f  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x6c44  throw
0x6c45  ldarg.0
0x6c46  ldarg.1
0x6c47  ldarg.2
0x6c48  ldarg.3
0x6c49  ldc.i4.0
0x6c4a  ldnull
0x6c4b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x6c50  ldarg.s  5
0x6c52  brfalse.s loc_6C64
0x6c54  ldarg.0
0x6c55  ldstr    aReferencedcoll// "ReferencedCollectionType"
0x6c5a  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6c5f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x6c64  ldarg.0
0x6c65  ldstr    aTypename_0// "TypeName"
0x6c6a  ldstr    asc_3D8E0// ""
0x6c6f  ldarg.3
0x6c70  callvirt instance string System.Web.Compilation.WCFModel.ReferencedCollectionType::get_TypeName()
0x6c75  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6c7a  ldarg.0
0x6c7b  ldstr    aCategory// "Category"
0x6c80  ldstr    asc_3D8E0// ""
0x6c85  ldarg.0
0x6c86  ldarg.3
0x6c87  callvirt instance valuetype CollectionCategory System.Web.Compilation.WCFModel.ReferencedCollectionType::get_Category()
0x6c8c  call     instance string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write4_CollectionCategory(valuetype CollectionCategory v)
0x6c91  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6c96  ldarg.0
0x6c97  ldarg.3
0x6c98  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x6c9d  ret
```
