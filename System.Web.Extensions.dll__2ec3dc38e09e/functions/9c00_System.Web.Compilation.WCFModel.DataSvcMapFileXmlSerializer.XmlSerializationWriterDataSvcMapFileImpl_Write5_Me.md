# System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write5_MetadataFile

- ea: `0x9c00`
- end: `0x9d38`
- name: `System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write5_MetadataFile`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x9920`

## callees

- `0x1d40`
- `0x26f0`
- `0x2710`
- `0x2730`
- `0x2750`
- `0x2770`
- `0x2790`
- `0x2800`
- `0x2830`
- `0x2860`
- `0x9c00`
- `0x9d40`

## string_xrefs

- `0x9c4a`: `urn:schemas-microsoft-com:xml-dataservicemap`

## pseudocode

```c

```

## disassembly

```asm
0x9c00  ldarg.3
0x9c01  brtrue.s loc_9C10
0x9c03  ldarg.s  4
0x9c05  brfalse.s loc_9C0F
0x9c07  ldarg.0
0x9c08  ldarg.1
0x9c09  ldarg.2
0x9c0a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x9c0f  ret
0x9c10  ldarg.s  5
0x9c12  brtrue.s loc_9C35
0x9c14  ldarg.3
0x9c15  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x9c1a  stloc.0
0x9c1b  ldloc.0
0x9c1c  ldtoken  System.Web.Compilation.WCFModel.MetadataFile
0x9c21  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9c26  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9c2b  brtrue.s loc_9C35
0x9c2d  ldarg.0
0x9c2e  ldarg.3
0x9c2f  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x9c34  throw
0x9c35  ldarg.0
0x9c36  ldarg.1
0x9c37  ldarg.2
0x9c38  ldarg.3
0x9c39  ldc.i4.0
0x9c3a  ldnull
0x9c3b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x9c40  ldarg.s  5
0x9c42  brfalse.s loc_9C54
0x9c44  ldarg.0
0x9c45  ldstr    aMetadatafile// "MetadataFile"
0x9c4a  ldstr    aUrnSchemasMicr_11// "urn:schemas-microsoft-com:xml-dataservi"...
0x9c4f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x9c54  ldarg.0
0x9c55  ldstr    aFilename_0// "FileName"
0x9c5a  ldstr    asc_3D8E0// ""
0x9c5f  ldarg.3
0x9c60  callvirt instance string System.Web.Compilation.WCFModel.ExternalFile::get_FileName()
0x9c65  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x9c6a  ldarg.0
0x9c6b  ldstr    aMetadatatype// "MetadataType"
0x9c70  ldstr    asc_3D8E0// ""
0x9c75  ldarg.0
0x9c76  ldarg.3
0x9c77  callvirt instance valuetype MetadataType System.Web.Compilation.WCFModel.MetadataFile::get_FileType()
0x9c7c  call     instance string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write4_MetadataType(valuetype MetadataType v)
0x9c81  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x9c86  ldarg.0
0x9c87  ldstr    aId// "ID"
0x9c8c  ldstr    asc_3D8E0// ""
0x9c91  ldarg.3
0x9c92  callvirt instance string System.Web.Compilation.WCFModel.MetadataFile::get_ID()
0x9c97  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x9c9c  ldarg.3
0x9c9d  callvirt instance bool System.Web.Compilation.WCFModel.MetadataFile::get_IgnoreSpecified()
0x9ca2  brfalse.s loc_9CBF
0x9ca4  ldarg.0
0x9ca5  ldstr    aIgnore// "Ignore"
0x9caa  ldstr    asc_3D8E0// ""
0x9caf  ldarg.3
0x9cb0  callvirt instance bool System.Web.Compilation.WCFModel.MetadataFile::get_Ignore()
0x9cb5  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x9cba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x9cbf  ldarg.3
0x9cc0  callvirt instance bool System.Web.Compilation.WCFModel.MetadataFile::get_IsMergeResultSpecified()
0x9cc5  brfalse.s loc_9CE2
0x9cc7  ldarg.0
0x9cc8  ldstr    aIsmergeresult// "IsMergeResult"
0x9ccd  ldstr    asc_3D8E0// ""
0x9cd2  ldarg.3
0x9cd3  callvirt instance bool System.Web.Compilation.WCFModel.MetadataFile::get_IsMergeResult()
0x9cd8  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x9cdd  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x9ce2  ldarg.3
0x9ce3  callvirt instance bool System.Web.Compilation.WCFModel.MetadataFile::get_SourceIdSpecified()
0x9ce8  brfalse.s loc_9D05
0x9cea  ldarg.0
0x9ceb  ldstr    aSourceid// "SourceId"
0x9cf0  ldstr    asc_3D8E0// ""
0x9cf5  ldarg.3
0x9cf6  callvirt instance int32 System.Web.Compilation.WCFModel.MetadataFile::get_SourceId()
0x9cfb  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x9d00  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x9d05  ldarg.0
0x9d06  ldstr    aSourceurl// "SourceUrl"
0x9d0b  ldstr    asc_3D8E0// ""
0x9d10  ldarg.3
0x9d11  callvirt instance string System.Web.Compilation.WCFModel.MetadataFile::get_SourceUrl()
0x9d16  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x9d1b  ldarg.3
0x9d1c  callvirt instance bool System.Web.Compilation.WCFModel.MetadataFile::get_IgnoreSpecified()
0x9d21  pop
0x9d22  ldarg.3
0x9d23  callvirt instance bool System.Web.Compilation.WCFModel.MetadataFile::get_IsMergeResultSpecified()
0x9d28  pop
0x9d29  ldarg.3
0x9d2a  callvirt instance bool System.Web.Compilation.WCFModel.MetadataFile::get_SourceIdSpecified()
0x9d2f  pop
0x9d30  ldarg.0
0x9d31  ldarg.3
0x9d32  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x9d37  ret
```
