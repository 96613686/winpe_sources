# System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::Read2_MetadataSource

- ea: `0xad90`
- end: `0xaf99`
- name: `System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::Read2_MetadataSource`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x9f20`

## callees

- `0x2ce0`
- `0x2d80`
- `0x2db0`
- `0x2de0`
- `0xad90`

## string_xrefs

- `0xaed3`: `:Address, :Protocol, :SourceId`

## pseudocode

```c

```

## disassembly

```asm
0xad90  ldarg.2
0xad91  brtrue.s loc_AD96
0xad93  ldnull
0xad94  br.s     loc_AD9C
0xad96  ldarg.0
0xad97  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0xad9c  stloc.0
0xad9d  ldc.i4.0
0xad9e  stloc.1
0xad9f  ldarg.1
0xada0  brfalse.s loc_ADA9
0xada2  ldarg.0
0xada3  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0xada8  stloc.1
0xada9  ldarg.2
0xadaa  brfalse.s loc_ADD9
0xadac  ldloc.0
0xadad  ldnull
0xadae  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0xadb3  brtrue.s loc_ADD9
0xadb5  ldloc.0
0xadb6  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0xadbb  ldarg.0
0xadbc  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id7_MetadataSource
0xadc1  bne.un.s loc_ADD1
0xadc3  ldloc.0
0xadc4  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0xadc9  ldarg.0
0xadca  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id2_Item
0xadcf  beq.s    loc_ADD9
0xadd1  ldarg.0
0xadd2  ldloc.0
0xadd3  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0xadd8  throw
0xadd9  ldloc.1
0xadda  brfalse.s loc_ADDE
0xaddc  ldnull
0xaddd  ret
0xadde  newobj   instance void System.Web.Compilation.WCFModel.MetadataSource::.ctor()
0xade3  stloc.2
0xade4  ldc.i4.3
0xade5  newarr   [mscorlib]System.Boolean
0xadea  stloc.3
0xadeb  br       loc_AEDD
0xadf0  ldloc.3
0xadf1  ldc.i4.0
0xadf2  ldelem.u1
0xadf3  brtrue.s loc_AE35
0xadf5  ldarg.0
0xadf6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xadfb  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xae00  ldarg.0
0xae01  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id22_Address
0xae06  bne.un.s loc_AE35
0xae08  ldarg.0
0xae09  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xae0e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xae13  ldarg.0
0xae14  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id5_Item
0xae19  bne.un.s loc_AE35
0xae1b  ldloc.2
0xae1c  ldarg.0
0xae1d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xae22  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0xae27  callvirt instance void System.Web.Compilation.WCFModel.MetadataSource::set_Address(string value)
0xae2c  ldloc.3
0xae2d  ldc.i4.0
0xae2e  ldc.i4.1
0xae2f  stelem.i1
0xae30  br       loc_AEDD
0xae35  ldloc.3
0xae36  ldc.i4.1
0xae37  ldelem.u1
0xae38  brtrue.s loc_AE77
0xae3a  ldarg.0
0xae3b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xae40  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xae45  ldarg.0
0xae46  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id23_Protocol
0xae4b  bne.un.s loc_AE77
0xae4d  ldarg.0
0xae4e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xae53  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xae58  ldarg.0
0xae59  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id5_Item
0xae5e  bne.un.s loc_AE77
0xae60  ldloc.2
0xae61  ldarg.0
0xae62  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xae67  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0xae6c  callvirt instance void System.Web.Compilation.WCFModel.MetadataSource::set_Protocol(string value)
0xae71  ldloc.3
0xae72  ldc.i4.1
0xae73  ldc.i4.1
0xae74  stelem.i1
0xae75  br.s     loc_AEDD
0xae77  ldloc.3
0xae78  ldc.i4.2
0xae79  ldelem.u1
0xae7a  brtrue.s loc_AEBE
0xae7c  ldarg.0
0xae7d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xae82  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xae87  ldarg.0
0xae88  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id20_SourceId
0xae8d  bne.un.s loc_AEBE
0xae8f  ldarg.0
0xae90  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xae95  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xae9a  ldarg.0
0xae9b  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id5_Item
0xaea0  bne.un.s loc_AEBE
0xaea2  ldloc.2
0xaea3  ldarg.0
0xaea4  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaea9  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0xaeae  call     int32 [System.Xml]System.Xml.XmlConvert::ToInt32(string)
0xaeb3  callvirt instance void System.Web.Compilation.WCFModel.MetadataSource::set_SourceId(int32 value)
0xaeb8  ldloc.3
0xaeb9  ldc.i4.2
0xaeba  ldc.i4.1
0xaebb  stelem.i1
0xaebc  br.s     loc_AEDD
0xaebe  ldarg.0
0xaebf  ldarg.0
0xaec0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaec5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xaeca  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0xaecf  brtrue.s loc_AEDD
0xaed1  ldarg.0
0xaed2  ldloc.2
0xaed3  ldstr    aAddressProtoco// ":Address, :Protocol, :SourceId"
0xaed8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0xaedd  ldarg.0
0xaede  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaee3  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0xaee8  brtrue   loc_ADF0
0xaeed  ldarg.0
0xaeee  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaef3  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0xaef8  pop
0xaef9  ldarg.0
0xaefa  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaeff  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xaf04  brfalse.s loc_AF13
0xaf06  ldarg.0
0xaf07  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf0c  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xaf11  ldloc.2
0xaf12  ret
0xaf13  ldarg.0
0xaf14  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf19  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0xaf1e  ldarg.0
0xaf1f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf24  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xaf29  pop
0xaf2a  ldc.i4.0
0xaf2b  stloc.s  4
0xaf2d  ldarg.0
0xaf2e  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0xaf33  stloc.s  5
0xaf35  br.s     loc_AF75
0xaf37  ldarg.0
0xaf38  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf3d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xaf42  ldc.i4.1
0xaf43  bne.un.s loc_AF53
0xaf45  ldarg.0
0xaf46  ldloc.2
0xaf47  ldstr    asc_3D8E0// ""
0xaf4c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0xaf51  br.s     loc_AF5F
0xaf53  ldarg.0
0xaf54  ldloc.2
0xaf55  ldstr    asc_3D8E0// ""
0xaf5a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0xaf5f  ldarg.0
0xaf60  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf65  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xaf6a  pop
0xaf6b  ldarg.0
0xaf6c  ldloca.s 4
0xaf6e  ldloca.s 5
0xaf70  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0xaf75  ldarg.0
0xaf76  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf7b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xaf80  ldc.i4.s 0xF
0xaf82  beq.s    loc_AF91
0xaf84  ldarg.0
0xaf85  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf8a  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xaf8f  brtrue.s loc_AF37
0xaf91  ldarg.0
0xaf92  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0xaf97  ldloc.2
0xaf98  ret
```
