# System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write2_MetadataSource

- ea: `0x9dc0`
- end: `0x9e63`
- name: `System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write2_MetadataSource`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x9920`

## callees

- `0x2d70`
- `0x2da0`
- `0x2dd0`
- `0x9dc0`

## string_xrefs

- `0x9e2b`: `Protocol`
- `0x9e0a`: `urn:schemas-microsoft-com:xml-dataservicemap`

## pseudocode

```c

```

## disassembly

```asm
0x9dc0  ldarg.3
0x9dc1  brtrue.s loc_9DD0
0x9dc3  ldarg.s  4
0x9dc5  brfalse.s loc_9DCF
0x9dc7  ldarg.0
0x9dc8  ldarg.1
0x9dc9  ldarg.2
0x9dca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x9dcf  ret
0x9dd0  ldarg.s  5
0x9dd2  brtrue.s loc_9DF5
0x9dd4  ldarg.3
0x9dd5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x9dda  stloc.0
0x9ddb  ldloc.0
0x9ddc  ldtoken  System.Web.Compilation.WCFModel.MetadataSource
0x9de1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9de6  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9deb  brtrue.s loc_9DF5
0x9ded  ldarg.0
0x9dee  ldarg.3
0x9def  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x9df4  throw
0x9df5  ldarg.0
0x9df6  ldarg.1
0x9df7  ldarg.2
0x9df8  ldarg.3
0x9df9  ldc.i4.0
0x9dfa  ldnull
0x9dfb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x9e00  ldarg.s  5
0x9e02  brfalse.s loc_9E14
0x9e04  ldarg.0
0x9e05  ldstr    aMetadatasource_0// "MetadataSource"
0x9e0a  ldstr    aUrnSchemasMicr_11// "urn:schemas-microsoft-com:xml-dataservi"...
0x9e0f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x9e14  ldarg.0
0x9e15  ldstr    aAddress_0// "Address"
0x9e1a  ldstr    asc_3D8E0// ""
0x9e1f  ldarg.3
0x9e20  callvirt instance string System.Web.Compilation.WCFModel.MetadataSource::get_Address()
0x9e25  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x9e2a  ldarg.0
0x9e2b  ldstr    aProtocol_0// "Protocol"
0x9e30  ldstr    asc_3D8E0// ""
0x9e35  ldarg.3
0x9e36  callvirt instance string System.Web.Compilation.WCFModel.MetadataSource::get_Protocol()
0x9e3b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x9e40  ldarg.0
0x9e41  ldstr    aSourceid// "SourceId"
0x9e46  ldstr    asc_3D8E0// ""
0x9e4b  ldarg.3
0x9e4c  callvirt instance int32 System.Web.Compilation.WCFModel.MetadataSource::get_SourceId()
0x9e51  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x9e56  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x9e5b  ldarg.0
0x9e5c  ldarg.3
0x9e5d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x9e62  ret
```
