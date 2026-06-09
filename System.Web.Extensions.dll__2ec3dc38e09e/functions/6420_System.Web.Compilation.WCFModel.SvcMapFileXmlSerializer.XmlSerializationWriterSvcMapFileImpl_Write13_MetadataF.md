# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write13_MetadataFile

- ea: `0x6420`
- end: `0x6558`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write13_MetadataFile`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6210`

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
- `0x6420`
- `0x6560`

## string_xrefs

- `0x646a`: `urn:schemas-microsoft-com:xml-wcfservicemap`

## pseudocode

```c

```

## disassembly

```asm
0x6420  ldarg.3
0x6421  brtrue.s loc_6430
0x6423  ldarg.s  4
0x6425  brfalse.s loc_642F
0x6427  ldarg.0
0x6428  ldarg.1
0x6429  ldarg.2
0x642a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x642f  ret
0x6430  ldarg.s  5
0x6432  brtrue.s loc_6455
0x6434  ldarg.3
0x6435  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x643a  stloc.0
0x643b  ldloc.0
0x643c  ldtoken  System.Web.Compilation.WCFModel.MetadataFile
0x6441  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6446  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x644b  brtrue.s loc_6455
0x644d  ldarg.0
0x644e  ldarg.3
0x644f  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x6454  throw
0x6455  ldarg.0
0x6456  ldarg.1
0x6457  ldarg.2
0x6458  ldarg.3
0x6459  ldc.i4.0
0x645a  ldnull
0x645b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x6460  ldarg.s  5
0x6462  brfalse.s loc_6474
0x6464  ldarg.0
0x6465  ldstr    aMetadatafile// "MetadataFile"
0x646a  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x646f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x6474  ldarg.0
0x6475  ldstr    aFilename_0// "FileName"
0x647a  ldstr    asc_3D8E0// ""
0x647f  ldarg.3
0x6480  callvirt instance string System.Web.Compilation.WCFModel.ExternalFile::get_FileName()
0x6485  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x648a  ldarg.0
0x648b  ldstr    aMetadatatype// "MetadataType"
0x6490  ldstr    asc_3D8E0// ""
0x6495  ldarg.0
0x6496  ldarg.3
0x6497  callvirt instance valuetype MetadataType System.Web.Compilation.WCFModel.MetadataFile::get_FileType()
0x649c  call     instance string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write12_MetadataType(valuetype MetadataType v)
0x64a1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x64a6  ldarg.0
0x64a7  ldstr    aId// "ID"
0x64ac  ldstr    asc_3D8E0// ""
0x64b1  ldarg.3
0x64b2  callvirt instance string System.Web.Compilation.WCFModel.MetadataFile::get_ID()
0x64b7  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x64bc  ldarg.3
0x64bd  callvirt instance bool System.Web.Compilation.WCFModel.MetadataFile::get_IgnoreSpecified()
0x64c2  brfalse.s loc_64DF
0x64c4  ldarg.0
0x64c5  ldstr    aIgnore// "Ignore"
0x64ca  ldstr    asc_3D8E0// ""
0x64cf  ldarg.3
0x64d0  callvirt instance bool System.Web.Compilation.WCFModel.MetadataFile::get_Ignore()
0x64d5  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x64da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x64df  ldarg.3
0x64e0  callvirt instance bool System.Web.Compilation.WCFModel.MetadataFile::get_IsMergeResultSpecified()
0x64e5  brfalse.s loc_6502
0x64e7  ldarg.0
0x64e8  ldstr    aIsmergeresult// "IsMergeResult"
0x64ed  ldstr    asc_3D8E0// ""
0x64f2  ldarg.3
0x64f3  callvirt instance bool System.Web.Compilation.WCFModel.MetadataFile::get_IsMergeResult()
0x64f8  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x64fd  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6502  ldarg.3
0x6503  callvirt instance bool System.Web.Compilation.WCFModel.MetadataFile::get_SourceIdSpecified()
0x6508  brfalse.s loc_6525
0x650a  ldarg.0
0x650b  ldstr    aSourceid// "SourceId"
0x6510  ldstr    asc_3D8E0// ""
0x6515  ldarg.3
0x6516  callvirt instance int32 System.Web.Compilation.WCFModel.MetadataFile::get_SourceId()
0x651b  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x6520  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6525  ldarg.0
0x6526  ldstr    aSourceurl// "SourceUrl"
0x652b  ldstr    asc_3D8E0// ""
0x6530  ldarg.3
0x6531  callvirt instance string System.Web.Compilation.WCFModel.MetadataFile::get_SourceUrl()
0x6536  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x653b  ldarg.3
0x653c  callvirt instance bool System.Web.Compilation.WCFModel.MetadataFile::get_IgnoreSpecified()
0x6541  pop
0x6542  ldarg.3
0x6543  callvirt instance bool System.Web.Compilation.WCFModel.MetadataFile::get_IsMergeResultSpecified()
0x6548  pop
0x6549  ldarg.3
0x654a  callvirt instance bool System.Web.Compilation.WCFModel.MetadataFile::get_SourceIdSpecified()
0x654f  pop
0x6550  ldarg.0
0x6551  ldarg.3
0x6552  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x6557  ret
```
