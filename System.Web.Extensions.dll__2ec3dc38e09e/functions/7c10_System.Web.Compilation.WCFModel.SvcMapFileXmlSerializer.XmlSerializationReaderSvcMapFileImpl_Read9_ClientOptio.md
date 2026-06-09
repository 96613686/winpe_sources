# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::Read9_ClientOptions

- ea: `0x7c10`
- end: `0x8810`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::Read9_ClientOptions`
- size: `3072`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6e50`

## callees

- `0x1630`
- `0x1660`
- `0x16a0`
- `0x16b0`
- `0x16e0`
- `0x1700`
- `0x1720`
- `0x1730`
- `0x1750`
- `0x1780`
- `0x17a0`
- `0x17d0`
- `0x1810`
- `0x1840`
- `0x1850`
- `0x1870`
- `0x1890`
- `0x18b0`
- `0x7c10`
- `0x8810`
- `0x8a20`
- `0x8ba0`
- `0x8d20`
- `0x8d70`
- `0x8f90`

## string_xrefs

- `0x7ee6`: `urn:schemas-microsoft-com:xml-wcfservicemap:ExcludedType`
- `0x7ef4`: `urn:schemas-microsoft-com:xml-wcfservicemap:ExcludedType`
- `0x8101`: `urn:schemas-microsoft-com:xml-wcfservicemap:NamespaceMapping`
- `0x810f`: `urn:schemas-microsoft-com:xml-wcfservicemap:NamespaceMapping`
- `0x8238`: `urn:schemas-microsoft-com:xml-wcfservicemap:CollectionMapping`
- `0x8246`: `urn:schemas-microsoft-com:xml-wcfservicemap:CollectionMapping`
- `0x84f6`: `urn:schemas-microsoft-com:xml-wcfservicemap:ReferencedAssembly`
- `0x8504`: `urn:schemas-microsoft-com:xml-wcfservicemap:ReferencedAssembly`
- `0x862d`: `urn:schemas-microsoft-com:xml-wcfservicemap:ReferencedDataContractType`
- `0x863b`: `urn:schemas-microsoft-com:xml-wcfservicemap:ReferencedDataContractType`
- `0x8764`: `urn:schemas-microsoft-com:xml-wcfservicemap:ServiceContractMapping`
- `0x8772`: `urn:schemas-microsoft-com:xml-wcfservicemap:ServiceContractMapping`
- `0x87bb`: `urn:schemas-microsoft-com:xml-wcfservicemap:GenerateAsynchronousMethods, urn:schemas-microsoft-com:xml-wcfservicemap:GenerateTaskBasedAsynchronousMethod, urn:schemas-microsoft-com:xml-wcfservicemap:EnableDataBinding, urn:schemas-microsoft-com:xml-wcfservicemap:ExcludedTypes, urn:schemas-microsoft-com:xml-wcfservicemap:ImportXmlTypes, urn:schemas-microsoft-com:xml-wcfservicemap:GenerateInternalTypes, urn:schemas-microsoft-com:xml-wcfservicemap:GenerateMessageContracts, urn:schemas-microsoft-com:x`
- `0x87c9`: `urn:schemas-microsoft-com:xml-wcfservicemap:GenerateAsynchronousMethods, urn:schemas-microsoft-com:xml-wcfservicemap:GenerateTaskBasedAsynchronousMethod, urn:schemas-microsoft-com:xml-wcfservicemap:EnableDataBinding, urn:schemas-microsoft-com:xml-wcfservicemap:ExcludedTypes, urn:schemas-microsoft-com:xml-wcfservicemap:ImportXmlTypes, urn:schemas-microsoft-com:xml-wcfservicemap:GenerateInternalTypes, urn:schemas-microsoft-com:xml-wcfservicemap:GenerateMessageContracts, urn:schemas-microsoft-com:x`

## pseudocode

```c

```

## disassembly

```asm
0x7c10  ldarg.2
0x7c11  brtrue.s loc_7C16
0x7c13  ldnull
0x7c14  br.s     loc_7C1C
0x7c16  ldarg.0
0x7c17  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x7c1c  stloc.0
0x7c1d  ldc.i4.0
0x7c1e  stloc.1
0x7c1f  ldarg.1
0x7c20  brfalse.s loc_7C29
0x7c22  ldarg.0
0x7c23  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x7c28  stloc.1
0x7c29  ldarg.2
0x7c2a  brfalse.s loc_7C59
0x7c2c  ldloc.0
0x7c2d  ldnull
0x7c2e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x7c33  brtrue.s loc_7C59
0x7c35  ldloc.0
0x7c36  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x7c3b  ldarg.0
0x7c3c  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id6_ClientOptions
0x7c41  bne.un.s loc_7C51
0x7c43  ldloc.0
0x7c44  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x7c49  ldarg.0
0x7c4a  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id2_Item
0x7c4f  beq.s    loc_7C59
0x7c51  ldarg.0
0x7c52  ldloc.0
0x7c53  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x7c58  throw
0x7c59  ldloc.1
0x7c5a  brfalse.s loc_7C5E
0x7c5c  ldnull
0x7c5d  ret
0x7c5e  newobj   instance void System.Web.Compilation.WCFModel.ClientOptions::.ctor()
0x7c63  stloc.2
0x7c64  ldloc.2
0x7c65  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ReferencedType> System.Web.Compilation.WCFModel.ClientOptions::get_ExcludedTypeList()
0x7c6a  stloc.3
0x7c6b  ldloc.2
0x7c6c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.NamespaceMapping> System.Web.Compilation.WCFModel.ClientOptions::get_NamespaceMappingList()
0x7c71  stloc.s  4
0x7c73  ldloc.2
0x7c74  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ReferencedCollectionType> System.Web.Compilation.WCFModel.ClientOptions::get_CollectionMappingList()
0x7c79  stloc.s  5
0x7c7b  ldloc.2
0x7c7c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ReferencedAssembly> System.Web.Compilation.WCFModel.ClientOptions::get_ReferencedAssemblyList()
0x7c81  stloc.s  6
0x7c83  ldloc.2
0x7c84  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ReferencedType> System.Web.Compilation.WCFModel.ClientOptions::get_ReferencedDataContractTypeList()
0x7c89  stloc.s  7
0x7c8b  ldloc.2
0x7c8c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ContractMapping> System.Web.Compilation.WCFModel.ClientOptions::get_ServiceContractMappingList()
0x7c91  stloc.s  8
0x7c93  ldc.i4.s 0x11
0x7c95  newarr   [mscorlib]System.Boolean
0x7c9a  stloc.s  9
0x7c9c  br.s     loc_7CB8
0x7c9e  ldarg.0
0x7c9f  ldarg.0
0x7ca0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7ca5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x7caa  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x7caf  brtrue.s loc_7CB8
0x7cb1  ldarg.0
0x7cb2  ldloc.2
0x7cb3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0x7cb8  ldarg.0
0x7cb9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7cbe  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x7cc3  brtrue.s loc_7C9E
0x7cc5  ldarg.0
0x7cc6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7ccb  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x7cd0  pop
0x7cd1  ldarg.0
0x7cd2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7cd7  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x7cdc  brfalse.s loc_7CEB
0x7cde  ldarg.0
0x7cdf  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7ce4  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x7ce9  ldloc.2
0x7cea  ret
0x7ceb  ldarg.0
0x7cec  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7cf1  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x7cf6  ldarg.0
0x7cf7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7cfc  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x7d01  pop
0x7d02  ldc.i4.0
0x7d03  stloc.s  0xA
0x7d05  ldarg.0
0x7d06  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x7d0b  stloc.s  0xB
0x7d0d  br       loc_87E9
0x7d12  ldarg.0
0x7d13  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7d18  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x7d1d  ldc.i4.1
0x7d1e  bne.un   loc_87C7
0x7d23  ldloc.s  9
0x7d25  ldc.i4.0
0x7d26  ldelem.u1
0x7d27  brtrue.s loc_7D6F
0x7d29  ldarg.0
0x7d2a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7d2f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x7d34  ldarg.0
0x7d35  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id22_GenerateAsynchronousMethods
0x7d3a  bne.un.s loc_7D6F
0x7d3c  ldarg.0
0x7d3d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7d42  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x7d47  ldarg.0
0x7d48  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id2_Item
0x7d4d  bne.un.s loc_7D6F
0x7d4f  ldloc.2
0x7d50  ldarg.0
0x7d51  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7d56  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x7d5b  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x7d60  callvirt instance void System.Web.Compilation.WCFModel.ClientOptions::set_GenerateAsynchronousMethods(bool value)
0x7d65  ldloc.s  9
0x7d67  ldc.i4.0
0x7d68  ldc.i4.1
0x7d69  stelem.i1
0x7d6a  br       loc_87D3
0x7d6f  ldloc.s  9
0x7d71  ldc.i4.1
0x7d72  ldelem.u1
0x7d73  brtrue.s loc_7DBB
0x7d75  ldarg.0
0x7d76  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7d7b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x7d80  ldarg.0
0x7d81  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id23_Item
0x7d86  bne.un.s loc_7DBB
0x7d88  ldarg.0
0x7d89  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7d8e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x7d93  ldarg.0
0x7d94  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id2_Item
0x7d99  bne.un.s loc_7DBB
0x7d9b  ldloc.2
0x7d9c  ldarg.0
0x7d9d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7da2  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x7da7  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x7dac  callvirt instance void System.Web.Compilation.WCFModel.ClientOptions::set_GenerateTaskBasedAsynchronousMethod(bool value)
0x7db1  ldloc.s  9
0x7db3  ldc.i4.1
0x7db4  ldc.i4.1
0x7db5  stelem.i1
0x7db6  br       loc_87D3
0x7dbb  ldloc.s  9
0x7dbd  ldc.i4.2
0x7dbe  ldelem.u1
0x7dbf  brtrue.s loc_7E07
0x7dc1  ldarg.0
0x7dc2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7dc7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x7dcc  ldarg.0
0x7dcd  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id24_EnableDataBinding
0x7dd2  bne.un.s loc_7E07
0x7dd4  ldarg.0
0x7dd5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7dda  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x7ddf  ldarg.0
0x7de0  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id2_Item
0x7de5  bne.un.s loc_7E07
0x7de7  ldloc.2
0x7de8  ldarg.0
0x7de9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7dee  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x7df3  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x7df8  callvirt instance void System.Web.Compilation.WCFModel.ClientOptions::set_EnableDataBinding(bool value)
0x7dfd  ldloc.s  9
0x7dff  ldc.i4.2
0x7e00  ldc.i4.1
0x7e01  stelem.i1
0x7e02  br       loc_87D3
0x7e07  ldarg.0
0x7e08  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7e0d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x7e12  ldarg.0
0x7e13  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id25_ExcludedTypes
0x7e18  bne.un   loc_7F3E
0x7e1d  ldarg.0
0x7e1e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7e23  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x7e28  ldarg.0
0x7e29  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id2_Item
0x7e2e  bne.un   loc_7F3E
0x7e33  ldarg.0
0x7e34  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x7e39  brtrue   loc_87D3
0x7e3e  ldloc.2
0x7e3f  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ReferencedType> System.Web.Compilation.WCFModel.ClientOptions::get_ExcludedTypeList()
0x7e44  stloc.s  0xC
0x7e46  ldloc.s  0xC
0x7e48  brfalse.s loc_7E57
0x7e4a  ldarg.0
0x7e4b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7e50  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x7e55  brfalse.s loc_7E67
0x7e57  ldarg.0
0x7e58  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7e5d  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x7e62  br       loc_87D3
0x7e67  ldarg.0
0x7e68  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7e6d  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x7e72  ldarg.0
0x7e73  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7e78  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x7e7d  pop
0x7e7e  ldc.i4.0
0x7e7f  stloc.s  0xD
0x7e81  ldarg.0
0x7e82  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x7e87  stloc.s  0xE
0x7e89  br       loc_7F14
0x7e8e  ldarg.0
0x7e8f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7e94  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x7e99  ldc.i4.1
0x7e9a  bne.un.s loc_7EF2
0x7e9c  ldarg.0
0x7e9d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7ea2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x7ea7  ldarg.0
0x7ea8  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id26_ExcludedType
0x7ead  bne.un.s loc_7EE4
0x7eaf  ldarg.0
0x7eb0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7eb5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x7eba  ldarg.0
0x7ebb  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id2_Item
0x7ec0  bne.un.s loc_7EE4
0x7ec2  ldloc.s  0xC
0x7ec4  brtrue.s loc_7ED3
0x7ec6  ldarg.0
0x7ec7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7ecc  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x7ed1  br.s     loc_7EFE
0x7ed3  ldloc.s  0xC
0x7ed5  ldarg.0
0x7ed6  ldc.i4.1
0x7ed7  ldc.i4.1
0x7ed8  call     instance class System.Web.Compilation.WCFModel.ReferencedType System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::Read2_ReferencedType(bool isNullable, bool checkType)
0x7edd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ReferencedType>::Add(var<u1>)
0x7ee2  br.s     loc_7EFE
0x7ee4  ldarg.0
0x7ee5  ldnull
0x7ee6  ldstr    aUrnSchemasMicr_4// "urn:schemas-microsoft-com:xml-wcfservic"...
0x7eeb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x7ef0  br.s     loc_7EFE
0x7ef2  ldarg.0
0x7ef3  ldnull
0x7ef4  ldstr    aUrnSchemasMicr_4// "urn:schemas-microsoft-com:xml-wcfservic"...
0x7ef9  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x7efe  ldarg.0
0x7eff  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7f04  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x7f09  pop
0x7f0a  ldarg.0
0x7f0b  ldloca.s 0xD
0x7f0d  ldloca.s 0xE
0x7f0f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x7f14  ldarg.0
0x7f15  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7f1a  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x7f1f  ldc.i4.s 0xF
0x7f21  beq.s    loc_7F33
0x7f23  ldarg.0
0x7f24  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7f29  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x7f2e  brtrue   loc_7E8E
0x7f33  ldarg.0
0x7f34  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x7f39  br       loc_87D3
0x7f3e  ldloc.s  9
0x7f40  ldc.i4.4
0x7f41  ldelem.u1
0x7f42  brtrue.s loc_7F8A
0x7f44  ldarg.0
0x7f45  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7f4a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x7f4f  ldarg.0
0x7f50  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id27_ImportXmlTypes
0x7f55  bne.un.s loc_7F8A
0x7f57  ldarg.0
0x7f58  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7f5d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
  ... truncated ...
```
