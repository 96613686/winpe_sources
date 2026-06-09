# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write10_MetadataSource

- ea: `0x65e0`
- end: `0x6683`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write10_MetadataSource`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6210`

## callees

- `0x2d70`
- `0x2da0`
- `0x2dd0`
- `0x65e0`

## string_xrefs

- `0x662a`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x664b`: `Protocol`

## pseudocode

```c

```

## disassembly

```asm
0x65e0  ldarg.3
0x65e1  brtrue.s loc_65F0
0x65e3  ldarg.s  4
0x65e5  brfalse.s loc_65EF
0x65e7  ldarg.0
0x65e8  ldarg.1
0x65e9  ldarg.2
0x65ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x65ef  ret
0x65f0  ldarg.s  5
0x65f2  brtrue.s loc_6615
0x65f4  ldarg.3
0x65f5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x65fa  stloc.0
0x65fb  ldloc.0
0x65fc  ldtoken  System.Web.Compilation.WCFModel.MetadataSource
0x6601  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6606  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x660b  brtrue.s loc_6615
0x660d  ldarg.0
0x660e  ldarg.3
0x660f  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x6614  throw
0x6615  ldarg.0
0x6616  ldarg.1
0x6617  ldarg.2
0x6618  ldarg.3
0x6619  ldc.i4.0
0x661a  ldnull
0x661b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x6620  ldarg.s  5
0x6622  brfalse.s loc_6634
0x6624  ldarg.0
0x6625  ldstr    aMetadatasource_0// "MetadataSource"
0x662a  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x662f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x6634  ldarg.0
0x6635  ldstr    aAddress_0// "Address"
0x663a  ldstr    asc_3D8E0// ""
0x663f  ldarg.3
0x6640  callvirt instance string System.Web.Compilation.WCFModel.MetadataSource::get_Address()
0x6645  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x664a  ldarg.0
0x664b  ldstr    aProtocol_0// "Protocol"
0x6650  ldstr    asc_3D8E0// ""
0x6655  ldarg.3
0x6656  callvirt instance string System.Web.Compilation.WCFModel.MetadataSource::get_Protocol()
0x665b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6660  ldarg.0
0x6661  ldstr    aSourceid// "SourceId"
0x6666  ldstr    asc_3D8E0// ""
0x666b  ldarg.3
0x666c  callvirt instance int32 System.Web.Compilation.WCFModel.MetadataSource::get_SourceId()
0x6671  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x6676  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x667b  ldarg.0
0x667c  ldarg.3
0x667d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x6682  ret
```
