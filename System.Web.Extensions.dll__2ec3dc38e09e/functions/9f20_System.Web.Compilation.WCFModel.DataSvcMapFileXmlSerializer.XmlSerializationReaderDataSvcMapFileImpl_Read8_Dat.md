# System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::Read8_DataSvcMapFileImpl

- ea: `0x9f20`
- end: `0xa5cf`
- name: `System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::Read8_DataSvcMapFileImpl`
- size: `1711`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x9eb0`

## callees

- `0x1a30`
- `0x1a50`
- `0x1a70`
- `0x1a90`
- `0x1ab0`
- `0x1ad0`
- `0x9f20`
- `0xa5d0`
- `0xa790`
- `0xa950`
- `0xad90`

## string_xrefs

- `0xa169`: `urn:schemas-microsoft-com:xml-dataservicemap:MetadataSource`
- `0xa177`: `urn:schemas-microsoft-com:xml-dataservicemap:MetadataSource`
- `0xa2a8`: `urn:schemas-microsoft-com:xml-dataservicemap:MetadataFile`
- `0xa2b6`: `urn:schemas-microsoft-com:xml-dataservicemap:MetadataFile`
- `0xa3e7`: `urn:schemas-microsoft-com:xml-dataservicemap:ExtensionFile`
- `0xa3f5`: `urn:schemas-microsoft-com:xml-dataservicemap:ExtensionFile`
- `0xa526`: `urn:schemas-microsoft-com:xml-dataservicemap:Parameter`
- `0xa534`: `urn:schemas-microsoft-com:xml-dataservicemap:Parameter`

## pseudocode

```c

```

## disassembly

```asm
0x9f20  ldarg.2
0x9f21  brtrue.s loc_9F26
0x9f23  ldnull
0x9f24  br.s     loc_9F2C
0x9f26  ldarg.0
0x9f27  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x9f2c  stloc.0
0x9f2d  ldc.i4.0
0x9f2e  stloc.1
0x9f2f  ldarg.1
0x9f30  brfalse.s loc_9F39
0x9f32  ldarg.0
0x9f33  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x9f38  stloc.1
0x9f39  ldarg.2
0x9f3a  brfalse.s loc_9F69
0x9f3c  ldloc.0
0x9f3d  ldnull
0x9f3e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x9f43  brtrue.s loc_9F69
0x9f45  ldloc.0
0x9f46  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x9f4b  ldarg.0
0x9f4c  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id3_DataSvcMapFileImpl
0x9f51  bne.un.s loc_9F61
0x9f53  ldloc.0
0x9f54  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x9f59  ldarg.0
0x9f5a  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id2_Item
0x9f5f  beq.s    loc_9F69
0x9f61  ldarg.0
0x9f62  ldloc.0
0x9f63  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x9f68  throw
0x9f69  ldloc.1
0x9f6a  brfalse.s loc_9F6E
0x9f6c  ldnull
0x9f6d  ret
0x9f6e  newobj   instance void System.Web.Compilation.WCFModel.DataSvcMapFileImpl::.ctor()
0x9f73  stloc.2
0x9f74  ldloc.2
0x9f75  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataSource> System.Web.Compilation.WCFModel.DataSvcMapFileImpl::get_MetadataSourceList()
0x9f7a  stloc.3
0x9f7b  ldloc.2
0x9f7c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataFile> System.Web.Compilation.WCFModel.DataSvcMapFileImpl::get_MetadataList()
0x9f81  stloc.s  4
0x9f83  ldloc.2
0x9f84  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ExtensionFile> System.Web.Compilation.WCFModel.DataSvcMapFileImpl::get_Extensions()
0x9f89  stloc.s  5
0x9f8b  ldloc.2
0x9f8c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.Parameter> System.Web.Compilation.WCFModel.DataSvcMapFileImpl::get_Parameters()
0x9f91  stloc.s  6
0x9f93  ldc.i4.5
0x9f94  newarr   [mscorlib]System.Boolean
0x9f99  stloc.s  7
0x9f9b  br.s     loc_A000
0x9f9d  ldloc.s  7
0x9f9f  ldc.i4.4
0x9fa0  ldelem.u1
0x9fa1  brtrue.s loc_9FE1
0x9fa3  ldarg.0
0x9fa4  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9fa9  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9fae  ldarg.0
0x9faf  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id4_ID
0x9fb4  bne.un.s loc_9FE1
0x9fb6  ldarg.0
0x9fb7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9fbc  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x9fc1  ldarg.0
0x9fc2  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id5_Item
0x9fc7  bne.un.s loc_9FE1
0x9fc9  ldloc.2
0x9fca  ldarg.0
0x9fcb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9fd0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x9fd5  callvirt instance void System.Web.Compilation.WCFModel.DataSvcMapFileImpl::set_ID(string value)
0x9fda  ldloc.s  7
0x9fdc  ldc.i4.4
0x9fdd  ldc.i4.1
0x9fde  stelem.i1
0x9fdf  br.s     loc_A000
0x9fe1  ldarg.0
0x9fe2  ldarg.0
0x9fe3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9fe8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x9fed  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x9ff2  brtrue.s loc_A000
0x9ff4  ldarg.0
0x9ff5  ldloc.2
0x9ff6  ldstr    aId_0// ":ID"
0x9ffb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0xa000  ldarg.0
0xa001  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa006  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0xa00b  brtrue.s loc_9F9D
0xa00d  ldarg.0
0xa00e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa013  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0xa018  pop
0xa019  ldarg.0
0xa01a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa01f  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xa024  brfalse.s loc_A033
0xa026  ldarg.0
0xa027  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa02c  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xa031  ldloc.2
0xa032  ret
0xa033  ldarg.0
0xa034  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa039  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0xa03e  ldc.i4.0
0xa03f  stloc.s  8
0xa041  ldarg.0
0xa042  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa047  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xa04c  pop
0xa04d  ldc.i4.0
0xa04e  stloc.s  9
0xa050  ldarg.0
0xa051  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0xa056  stloc.s  0xA
0xa058  br       loc_A5A8
0xa05d  ldarg.0
0xa05e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa063  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa068  ldc.i4.1
0xa069  bne.un   loc_A58A
0xa06e  ldloc.s  8
0xa070  switch   loc_A08A, loc_A1C9, loc_A308, loc_A447
0xa085  br       loc_A580
0xa08a  ldarg.0
0xa08b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa090  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa095  ldarg.0
0xa096  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id6_MetadataSources
0xa09b  bne.un   loc_A1C1
0xa0a0  ldarg.0
0xa0a1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa0a6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xa0ab  ldarg.0
0xa0ac  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id2_Item
0xa0b1  bne.un   loc_A1C1
0xa0b6  ldarg.0
0xa0b7  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0xa0bc  brtrue   loc_A592
0xa0c1  ldloc.2
0xa0c2  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataSource> System.Web.Compilation.WCFModel.DataSvcMapFileImpl::get_MetadataSourceList()
0xa0c7  stloc.s  0xB
0xa0c9  ldloc.s  0xB
0xa0cb  brfalse.s loc_A0DA
0xa0cd  ldarg.0
0xa0ce  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa0d3  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xa0d8  brfalse.s loc_A0EA
0xa0da  ldarg.0
0xa0db  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa0e0  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xa0e5  br       loc_A592
0xa0ea  ldarg.0
0xa0eb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa0f0  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0xa0f5  ldarg.0
0xa0f6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa0fb  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xa100  pop
0xa101  ldc.i4.0
0xa102  stloc.s  0xC
0xa104  ldarg.0
0xa105  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0xa10a  stloc.s  0xD
0xa10c  br       loc_A197
0xa111  ldarg.0
0xa112  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa117  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa11c  ldc.i4.1
0xa11d  bne.un.s loc_A175
0xa11f  ldarg.0
0xa120  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa125  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa12a  ldarg.0
0xa12b  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id7_MetadataSource
0xa130  bne.un.s loc_A167
0xa132  ldarg.0
0xa133  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa138  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xa13d  ldarg.0
0xa13e  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id2_Item
0xa143  bne.un.s loc_A167
0xa145  ldloc.s  0xB
0xa147  brtrue.s loc_A156
0xa149  ldarg.0
0xa14a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa14f  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xa154  br.s     loc_A181
0xa156  ldloc.s  0xB
0xa158  ldarg.0
0xa159  ldc.i4.1
0xa15a  ldc.i4.1
0xa15b  call     instance class System.Web.Compilation.WCFModel.MetadataSource System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::Read2_MetadataSource(bool isNullable, bool checkType)
0xa160  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataSource>::Add(var<u1>)
0xa165  br.s     loc_A181
0xa167  ldarg.0
0xa168  ldnull
0xa169  ldstr    aUrnSchemasMicr_13// "urn:schemas-microsoft-com:xml-dataservi"...
0xa16e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0xa173  br.s     loc_A181
0xa175  ldarg.0
0xa176  ldnull
0xa177  ldstr    aUrnSchemasMicr_13// "urn:schemas-microsoft-com:xml-dataservi"...
0xa17c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0xa181  ldarg.0
0xa182  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa187  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xa18c  pop
0xa18d  ldarg.0
0xa18e  ldloca.s 0xC
0xa190  ldloca.s 0xD
0xa192  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0xa197  ldarg.0
0xa198  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa19d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa1a2  ldc.i4.s 0xF
0xa1a4  beq.s    loc_A1B6
0xa1a6  ldarg.0
0xa1a7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa1ac  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa1b1  brtrue   loc_A111
0xa1b6  ldarg.0
0xa1b7  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0xa1bc  br       loc_A592
0xa1c1  ldc.i4.1
0xa1c2  stloc.s  8
0xa1c4  br       loc_A592
0xa1c9  ldarg.0
0xa1ca  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa1cf  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa1d4  ldarg.0
0xa1d5  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id8_Metadata
0xa1da  bne.un   loc_A300
0xa1df  ldarg.0
0xa1e0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa1e5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xa1ea  ldarg.0
0xa1eb  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id2_Item
0xa1f0  bne.un   loc_A300
0xa1f5  ldarg.0
0xa1f6  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0xa1fb  brtrue   loc_A592
0xa200  ldloc.2
0xa201  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataFile> System.Web.Compilation.WCFModel.DataSvcMapFileImpl::get_MetadataList()
0xa206  stloc.s  0xE
0xa208  ldloc.s  0xE
0xa20a  brfalse.s loc_A219
0xa20c  ldarg.0
0xa20d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa212  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xa217  brfalse.s loc_A229
0xa219  ldarg.0
0xa21a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa21f  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xa224  br       loc_A592
0xa229  ldarg.0
0xa22a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa22f  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0xa234  ldarg.0
0xa235  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa23a  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xa23f  pop
0xa240  ldc.i4.0
0xa241  stloc.s  0xF
0xa243  ldarg.0
0xa244  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0xa249  stloc.s  0x10
0xa24b  br       loc_A2D6
0xa250  ldarg.0
0xa251  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa256  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa25b  ldc.i4.1
0xa25c  bne.un.s loc_A2B4
0xa25e  ldarg.0
0xa25f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa264  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa269  ldarg.0
0xa26a  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id9_MetadataFile
0xa26f  bne.un.s loc_A2A6
0xa271  ldarg.0
0xa272  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa277  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xa27c  ldarg.0
0xa27d  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id2_Item
0xa282  bne.un.s loc_A2A6
0xa284  ldloc.s  0xE
0xa286  brtrue.s loc_A295
0xa288  ldarg.0
0xa289  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa28e  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xa293  br.s     loc_A2C0
0xa295  ldloc.s  0xE
  ... truncated ...
```
