# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::Read15_SvcMapFileImpl

- ea: `0x6e50`
- end: `0x73f4`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::Read15_SvcMapFileImpl`
- size: `1444`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x6de0`

## callees

- `0x3ec0`
- `0x3f00`
- `0x3f20`
- `0x3f40`
- `0x3f60`
- `0x3f80`
- `0x6e50`
- `0x7400`
- `0x75c0`
- `0x7a00`
- `0x7c10`

## string_xrefs

- `0x70cd`: `urn:schemas-microsoft-com:xml-wcfservicemap:MetadataSource`
- `0x70db`: `urn:schemas-microsoft-com:xml-wcfservicemap:MetadataSource`
- `0x720c`: `urn:schemas-microsoft-com:xml-wcfservicemap:MetadataFile`
- `0x721a`: `urn:schemas-microsoft-com:xml-wcfservicemap:MetadataFile`
- `0x734b`: `urn:schemas-microsoft-com:xml-wcfservicemap:ExtensionFile`
- `0x7359`: `urn:schemas-microsoft-com:xml-wcfservicemap:ExtensionFile`

## pseudocode

```c

```

## disassembly

```asm
0x6e50  ldarg.2
0x6e51  brtrue.s loc_6E56
0x6e53  ldnull
0x6e54  br.s     loc_6E5C
0x6e56  ldarg.0
0x6e57  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x6e5c  stloc.0
0x6e5d  ldc.i4.0
0x6e5e  stloc.1
0x6e5f  ldarg.1
0x6e60  brfalse.s loc_6E69
0x6e62  ldarg.0
0x6e63  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x6e68  stloc.1
0x6e69  ldarg.2
0x6e6a  brfalse.s loc_6E99
0x6e6c  ldloc.0
0x6e6d  ldnull
0x6e6e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x6e73  brtrue.s loc_6E99
0x6e75  ldloc.0
0x6e76  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x6e7b  ldarg.0
0x6e7c  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id3_SvcMapFileImpl
0x6e81  bne.un.s loc_6E91
0x6e83  ldloc.0
0x6e84  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x6e89  ldarg.0
0x6e8a  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id2_Item
0x6e8f  beq.s    loc_6E99
0x6e91  ldarg.0
0x6e92  ldloc.0
0x6e93  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x6e98  throw
0x6e99  ldloc.1
0x6e9a  brfalse.s loc_6E9E
0x6e9c  ldnull
0x6e9d  ret
0x6e9e  newobj   instance void System.Web.Compilation.WCFModel.SvcMapFileImpl::.ctor()
0x6ea3  stloc.2
0x6ea4  ldloc.2
0x6ea5  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataSource> System.Web.Compilation.WCFModel.SvcMapFileImpl::get_MetadataSourceList()
0x6eaa  stloc.3
0x6eab  ldloc.2
0x6eac  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataFile> System.Web.Compilation.WCFModel.SvcMapFileImpl::get_MetadataList()
0x6eb1  stloc.s  4
0x6eb3  ldloc.2
0x6eb4  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ExtensionFile> System.Web.Compilation.WCFModel.SvcMapFileImpl::get_Extensions()
0x6eb9  stloc.s  5
0x6ebb  ldc.i4.5
0x6ebc  newarr   [mscorlib]System.Boolean
0x6ec1  stloc.s  6
0x6ec3  br.s     loc_6F28
0x6ec5  ldloc.s  6
0x6ec7  ldc.i4.4
0x6ec8  ldelem.u1
0x6ec9  brtrue.s loc_6F09
0x6ecb  ldarg.0
0x6ecc  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6ed1  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x6ed6  ldarg.0
0x6ed7  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id4_ID
0x6edc  bne.un.s loc_6F09
0x6ede  ldarg.0
0x6edf  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6ee4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x6ee9  ldarg.0
0x6eea  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id5_Item
0x6eef  bne.un.s loc_6F09
0x6ef1  ldloc.2
0x6ef2  ldarg.0
0x6ef3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6ef8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x6efd  callvirt instance void System.Web.Compilation.WCFModel.SvcMapFileImpl::set_ID(string value)
0x6f02  ldloc.s  6
0x6f04  ldc.i4.4
0x6f05  ldc.i4.1
0x6f06  stelem.i1
0x6f07  br.s     loc_6F28
0x6f09  ldarg.0
0x6f0a  ldarg.0
0x6f0b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6f10  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x6f15  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x6f1a  brtrue.s loc_6F28
0x6f1c  ldarg.0
0x6f1d  ldloc.2
0x6f1e  ldstr    aId_0// ":ID"
0x6f23  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x6f28  ldarg.0
0x6f29  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6f2e  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x6f33  brtrue.s loc_6EC5
0x6f35  ldarg.0
0x6f36  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6f3b  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x6f40  pop
0x6f41  ldarg.0
0x6f42  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6f47  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x6f4c  brfalse.s loc_6F5B
0x6f4e  ldarg.0
0x6f4f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6f54  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x6f59  ldloc.2
0x6f5a  ret
0x6f5b  ldarg.0
0x6f5c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6f61  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x6f66  ldc.i4.0
0x6f67  stloc.s  7
0x6f69  ldarg.0
0x6f6a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6f6f  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x6f74  pop
0x6f75  ldc.i4.0
0x6f76  stloc.s  8
0x6f78  ldarg.0
0x6f79  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x6f7e  stloc.s  9
0x6f80  br       loc_73CD
0x6f85  ldarg.0
0x6f86  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6f8b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x6f90  ldc.i4.1
0x6f91  bne.un   loc_73AF
0x6f96  ldloc.s  7
0x6f98  switch   loc_6FB2, loc_6FEE, loc_712D, loc_726C
0x6fad  br       loc_73A5
0x6fb2  ldarg.0
0x6fb3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6fb8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x6fbd  ldarg.0
0x6fbe  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id6_ClientOptions
0x6fc3  bne.un.s loc_6FE6
0x6fc5  ldarg.0
0x6fc6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6fcb  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x6fd0  ldarg.0
0x6fd1  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id2_Item
0x6fd6  bne.un.s loc_6FE6
0x6fd8  ldloc.2
0x6fd9  ldarg.0
0x6fda  ldc.i4.0
0x6fdb  ldc.i4.1
0x6fdc  call     instance class System.Web.Compilation.WCFModel.ClientOptions System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::Read9_ClientOptions(bool isNullable, bool checkType)
0x6fe1  callvirt instance void System.Web.Compilation.WCFModel.SvcMapFileImpl::set_ClientOptions(class System.Web.Compilation.WCFModel.ClientOptions value)
0x6fe6  ldc.i4.1
0x6fe7  stloc.s  7
0x6fe9  br       loc_73B7
0x6fee  ldarg.0
0x6fef  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6ff4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x6ff9  ldarg.0
0x6ffa  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id7_MetadataSources
0x6fff  bne.un   loc_7125
0x7004  ldarg.0
0x7005  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x700a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x700f  ldarg.0
0x7010  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id2_Item
0x7015  bne.un   loc_7125
0x701a  ldarg.0
0x701b  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x7020  brtrue   loc_73B7
0x7025  ldloc.2
0x7026  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataSource> System.Web.Compilation.WCFModel.SvcMapFileImpl::get_MetadataSourceList()
0x702b  stloc.s  0xA
0x702d  ldloc.s  0xA
0x702f  brfalse.s loc_703E
0x7031  ldarg.0
0x7032  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7037  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x703c  brfalse.s loc_704E
0x703e  ldarg.0
0x703f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7044  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x7049  br       loc_73B7
0x704e  ldarg.0
0x704f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7054  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x7059  ldarg.0
0x705a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x705f  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x7064  pop
0x7065  ldc.i4.0
0x7066  stloc.s  0xB
0x7068  ldarg.0
0x7069  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x706e  stloc.s  0xC
0x7070  br       loc_70FB
0x7075  ldarg.0
0x7076  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x707b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x7080  ldc.i4.1
0x7081  bne.un.s loc_70D9
0x7083  ldarg.0
0x7084  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7089  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x708e  ldarg.0
0x708f  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id8_MetadataSource
0x7094  bne.un.s loc_70CB
0x7096  ldarg.0
0x7097  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x709c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x70a1  ldarg.0
0x70a2  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id2_Item
0x70a7  bne.un.s loc_70CB
0x70a9  ldloc.s  0xA
0x70ab  brtrue.s loc_70BA
0x70ad  ldarg.0
0x70ae  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x70b3  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x70b8  br.s     loc_70E5
0x70ba  ldloc.s  0xA
0x70bc  ldarg.0
0x70bd  ldc.i4.1
0x70be  ldc.i4.1
0x70bf  call     instance class System.Web.Compilation.WCFModel.MetadataSource System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::Read10_MetadataSource(bool isNullable, bool checkType)
0x70c4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataSource>::Add(var<u1>)
0x70c9  br.s     loc_70E5
0x70cb  ldarg.0
0x70cc  ldnull
0x70cd  ldstr    aUrnSchemasMicr_1// "urn:schemas-microsoft-com:xml-wcfservic"...
0x70d2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x70d7  br.s     loc_70E5
0x70d9  ldarg.0
0x70da  ldnull
0x70db  ldstr    aUrnSchemasMicr_1// "urn:schemas-microsoft-com:xml-wcfservic"...
0x70e0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x70e5  ldarg.0
0x70e6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x70eb  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x70f0  pop
0x70f1  ldarg.0
0x70f2  ldloca.s 0xB
0x70f4  ldloca.s 0xC
0x70f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x70fb  ldarg.0
0x70fc  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7101  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x7106  ldc.i4.s 0xF
0x7108  beq.s    loc_711A
0x710a  ldarg.0
0x710b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7110  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x7115  brtrue   loc_7075
0x711a  ldarg.0
0x711b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x7120  br       loc_73B7
0x7125  ldc.i4.2
0x7126  stloc.s  7
0x7128  br       loc_73B7
0x712d  ldarg.0
0x712e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7133  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x7138  ldarg.0
0x7139  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id9_Metadata
0x713e  bne.un   loc_7264
0x7143  ldarg.0
0x7144  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7149  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x714e  ldarg.0
0x714f  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id2_Item
0x7154  bne.un   loc_7264
0x7159  ldarg.0
0x715a  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x715f  brtrue   loc_73B7
0x7164  ldloc.2
0x7165  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataFile> System.Web.Compilation.WCFModel.SvcMapFileImpl::get_MetadataList()
0x716a  stloc.s  0xD
0x716c  ldloc.s  0xD
0x716e  brfalse.s loc_717D
0x7170  ldarg.0
0x7171  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7176  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x717b  brfalse.s loc_718D
0x717d  ldarg.0
0x717e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7183  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x7188  br       loc_73B7
0x718d  ldarg.0
0x718e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7193  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x7198  ldarg.0
0x7199  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x719e  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x71a3  pop
0x71a4  ldc.i4.0
0x71a5  stloc.s  0xE
0x71a7  ldarg.0
0x71a8  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x71ad  stloc.s  0xF
0x71af  br       loc_723A
0x71b4  ldarg.0
0x71b5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x71ba  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x71bf  ldc.i4.1
0x71c0  bne.un.s loc_7218
0x71c2  ldarg.0
  ... truncated ...
```
