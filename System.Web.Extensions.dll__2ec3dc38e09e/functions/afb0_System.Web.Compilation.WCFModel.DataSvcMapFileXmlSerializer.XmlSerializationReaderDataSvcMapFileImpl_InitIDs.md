# System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::InitIDs

- ea: `0xafb0`
- end: `0xb21e`
- name: `System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::InitIDs`
- size: `622`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0xb1f3`: `Extensions`
- `0xb079`: `ExtensionFile`
- `0xb151`: `Protocol`
- `0xb05e`: `urn:schemas-microsoft-com:xml-dataservicemap`

## pseudocode

```c

```

## disassembly

```asm
0xafb0  ldarg.0
0xafb1  ldarg.0
0xafb2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xafb7  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xafbc  ldstr    asc_3D8E0// ""
0xafc1  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xafc6  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id5_Item
0xafcb  ldarg.0
0xafcc  ldarg.0
0xafcd  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xafd2  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xafd7  ldstr    aId// "ID"
0xafdc  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xafe1  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id4_ID
0xafe6  ldarg.0
0xafe7  ldarg.0
0xafe8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xafed  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xaff2  ldstr    aIgnore// "Ignore"
0xaff7  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xaffc  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id18_Ignore
0xb001  ldarg.0
0xb002  ldarg.0
0xb003  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb008  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb00d  ldstr    aSourceurl// "SourceUrl"
0xb012  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb017  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id21_SourceUrl
0xb01c  ldarg.0
0xb01d  ldarg.0
0xb01e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb023  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb028  ldstr    aSourceid// "SourceId"
0xb02d  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb032  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id20_SourceId
0xb037  ldarg.0
0xb038  ldarg.0
0xb039  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb03e  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb043  ldstr    aName_0// "Name"
0xb048  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb04d  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id14_Name
0xb052  ldarg.0
0xb053  ldarg.0
0xb054  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb059  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb05e  ldstr    aUrnSchemasMicr_11// "urn:schemas-microsoft-com:xml-dataservi"...
0xb063  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb068  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id2_Item
0xb06d  ldarg.0
0xb06e  ldarg.0
0xb06f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb074  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb079  ldstr    aExtensionfile// "ExtensionFile"
0xb07e  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb083  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id11_ExtensionFile
0xb088  ldarg.0
0xb089  ldarg.0
0xb08a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb08f  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb094  ldstr    aParameters// "Parameters"
0xb099  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb09e  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id12_Parameters
0xb0a3  ldarg.0
0xb0a4  ldarg.0
0xb0a5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb0aa  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb0af  ldstr    aReferencegroup// "ReferenceGroup"
0xb0b4  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb0b9  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id1_ReferenceGroup
0xb0be  ldarg.0
0xb0bf  ldarg.0
0xb0c0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb0c5  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb0ca  ldstr    aFilename_0// "FileName"
0xb0cf  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb0d4  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id16_FileName
0xb0d9  ldarg.0
0xb0da  ldarg.0
0xb0db  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb0e0  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb0e5  ldstr    aMetadatasource// "MetadataSources"
0xb0ea  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb0ef  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id6_MetadataSources
0xb0f4  ldarg.0
0xb0f5  ldarg.0
0xb0f6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb0fb  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb100  ldstr    aMetadatatype// "MetadataType"
0xb105  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb10a  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id17_MetadataType
0xb10f  ldarg.0
0xb110  ldarg.0
0xb111  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb116  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb11b  ldstr    aParameter// "Parameter"
0xb120  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb125  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id13_Parameter
0xb12a  ldarg.0
0xb12b  ldarg.0
0xb12c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb131  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb136  ldstr    aValue_0// "Value"
0xb13b  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb140  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id15_Value
0xb145  ldarg.0
0xb146  ldarg.0
0xb147  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb14c  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb151  ldstr    aProtocol_0// "Protocol"
0xb156  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb15b  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id23_Protocol
0xb160  ldarg.0
0xb161  ldarg.0
0xb162  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb167  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb16c  ldstr    aDatasvcmapfile// "DataSvcMapFileImpl"
0xb171  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb176  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id3_DataSvcMapFileImpl
0xb17b  ldarg.0
0xb17c  ldarg.0
0xb17d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb182  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb187  ldstr    aMetadata// "Metadata"
0xb18c  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb191  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id8_Metadata
0xb196  ldarg.0
0xb197  ldarg.0
0xb198  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb19d  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb1a2  ldstr    aMetadatafile// "MetadataFile"
0xb1a7  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb1ac  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id9_MetadataFile
0xb1b1  ldarg.0
0xb1b2  ldarg.0
0xb1b3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb1b8  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb1bd  ldstr    aIsmergeresult// "IsMergeResult"
0xb1c2  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb1c7  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id19_IsMergeResult
0xb1cc  ldarg.0
0xb1cd  ldarg.0
0xb1ce  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb1d3  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb1d8  ldstr    aMetadatasource_0// "MetadataSource"
0xb1dd  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb1e2  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id7_MetadataSource
0xb1e7  ldarg.0
0xb1e8  ldarg.0
0xb1e9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb1ee  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb1f3  ldstr    aExtensions// "Extensions"
0xb1f8  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb1fd  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id10_Extensions
0xb202  ldarg.0
0xb203  ldarg.0
0xb204  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb209  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0xb20e  ldstr    aAddress_0// "Address"
0xb213  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0xb218  stfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id22_Address
0xb21d  ret
```
