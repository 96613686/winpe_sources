# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::InitIDs

- ea: `0x9160`
- end: `0x96dd`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::InitIDs`
- size: `1405`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x9445`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x962b`: `Extensions`
- `0x9460`: `ExtensionFile`
- `0x94e7`: `Protocol`
- `0x9496`: `GenerateTaskBasedAsynchronousMethod`
- `0x95da`: `ImportXmlTypes`
- `0x967c`: `ServiceContractMappings`
- `0x9502`: `ServiceContractMapping`

## pseudocode

```c

```

## disassembly

```asm
0x9160  ldarg.0
0x9161  ldarg.0
0x9162  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9167  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x916c  ldstr    aTypename_0// "TypeName"
0x9171  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x9176  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id47_TypeName
0x917b  ldarg.0
0x917c  ldarg.0
0x917d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9182  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x9187  ldstr    aReferencegroup// "ReferenceGroup"
0x918c  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x9191  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id1_ReferenceGroup
0x9196  ldarg.0
0x9197  ldarg.0
0x9198  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x919d  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x91a2  ldstr    aAssemblyname_0// "AssemblyName"
0x91a7  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x91ac  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id49_AssemblyName
0x91b1  ldarg.0
0x91b2  ldarg.0
0x91b3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x91b8  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x91bd  ldstr    aReferenceallas// "ReferenceAllAssemblies"
0x91c2  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x91c7  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id38_ReferenceAllAssemblies
0x91cc  ldarg.0
0x91cd  ldarg.0
0x91ce  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x91d3  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x91d8  ldstr    aTargetnamespac// "TargetNamespace"
0x91dd  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x91e2  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id46_TargetNamespace
0x91e7  ldarg.0
0x91e8  ldarg.0
0x91e9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x91ee  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x91f3  ldstr    aGeneratemessag// "GenerateMessageContracts"
0x91f8  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x91fd  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id29_GenerateMessageContracts
0x9202  ldarg.0
0x9203  ldarg.0
0x9204  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9209  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x920e  ldstr    aGenerateintern// "GenerateInternalTypes"
0x9213  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x9218  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id28_GenerateInternalTypes
0x921d  ldarg.0
0x921e  ldarg.0
0x921f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9224  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x9229  ldstr    aFilename_0// "FileName"
0x922e  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x9233  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id13_FileName
0x9238  ldarg.0
0x9239  ldarg.0
0x923a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x923f  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x9244  ldstr    aSvcmapfileimpl// "SvcMapFileImpl"
0x9249  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x924e  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id3_SvcMapFileImpl
0x9253  ldarg.0
0x9254  ldarg.0
0x9255  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x925a  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x925f  ldstr    aMetadatasource// "MetadataSources"
0x9264  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x9269  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id7_MetadataSources
0x926e  ldarg.0
0x926f  ldarg.0
0x9270  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9275  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x927a  ldstr    aReferencedcoll// "ReferencedCollectionType"
0x927f  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x9284  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id50_ReferencedCollectionType
0x9289  ldarg.0
0x928a  ldarg.0
0x928b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9290  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x9295  ldstr    aMetadatasource_0// "MetadataSource"
0x929a  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x929f  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id8_MetadataSource
0x92a4  ldarg.0
0x92a5  ldarg.0
0x92a6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x92ab  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x92b0  ldstr    aExcludedtypes// "ExcludedTypes"
0x92b5  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x92ba  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id25_ExcludedTypes
0x92bf  ldarg.0
0x92c0  ldarg.0
0x92c1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x92c6  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x92cb  ldstr    aMetadatafile// "MetadataFile"
0x92d0  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x92d5  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id10_MetadataFile
0x92da  ldarg.0
0x92db  ldarg.0
0x92dc  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x92e1  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x92e6  ldstr    aContractmappin// "ContractMapping"
0x92eb  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x92f0  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id45_ContractMapping
0x92f5  ldarg.0
0x92f6  ldarg.0
0x92f7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x92fc  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x9301  ldstr    aMetadatatype// "MetadataType"
0x9306  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x930b  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id15_MetadataType
0x9310  ldarg.0
0x9311  ldarg.0
0x9312  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9317  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x931c  ldstr    aGenerateserial// "GenerateSerializableTypes"
0x9321  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x9326  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id34_GenerateSerializableTypes
0x932b  ldarg.0
0x932c  ldarg.0
0x932d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9332  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x9337  ldstr    aNamespacemappi_0// "NamespaceMapping"
0x933c  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x9341  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id31_NamespaceMapping
0x9346  ldarg.0
0x9347  ldarg.0
0x9348  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x934d  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x9352  ldstr    aReferenceddata_0// "ReferencedDataContractType"
0x9357  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x935c  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id42_ReferencedDataContractType
0x9361  ldarg.0
0x9362  ldarg.0
0x9363  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9368  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x936d  ldstr    aIgnore// "Ignore"
0x9372  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x9377  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id16_Ignore
0x937c  ldarg.0
0x937d  ldarg.0
0x937e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9383  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x9388  ldstr    aUseserializerf// "UseSerializerForFaults"
0x938d  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x9392  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id36_UseSerializerForFaults
0x9397  ldarg.0
0x9398  ldarg.0
0x9399  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x939e  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x93a3  ldstr    aClrnamespace// "ClrNamespace"
0x93a8  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x93ad  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id52_ClrNamespace
0x93b2  ldarg.0
0x93b3  ldarg.0
0x93b4  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x93b9  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x93be  ldstr    aId// "ID"
0x93c3  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x93c8  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id4_ID
0x93cd  ldarg.0
0x93ce  ldarg.0
0x93cf  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x93d4  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x93d9  ldstr    aIsmergeresult// "IsMergeResult"
0x93de  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x93e3  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id17_IsMergeResult
0x93e8  ldarg.0
0x93e9  ldarg.0
0x93ea  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x93ef  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x93f4  ldstr    aReferencedasse_0// "ReferencedAssembly"
0x93f9  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x93fe  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id40_ReferencedAssembly
0x9403  ldarg.0
0x9404  ldarg.0
0x9405  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x940a  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x940f  ldstr    aReferencedtype// "ReferencedType"
0x9414  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x9419  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id48_ReferencedType
0x941e  ldarg.0
0x941f  ldarg.0
0x9420  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9425  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x942a  ldstr    aGenerateasynch// "GenerateAsynchronousMethods"
0x942f  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x9434  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id22_GenerateAsynchronousMethods
0x9439  ldarg.0
0x943a  ldarg.0
0x943b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9440  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x9445  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x944a  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x944f  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id2_Item
0x9454  ldarg.0
0x9455  ldarg.0
0x9456  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x945b  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x9460  ldstr    aExtensionfile// "ExtensionFile"
0x9465  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x946a  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id12_ExtensionFile
0x946f  ldarg.0
0x9470  ldarg.0
0x9471  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9476  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x947b  ldstr    aCollectionmapp// "CollectionMappings"
0x9480  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x9485  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id32_CollectionMappings
0x948a  ldarg.0
0x948b  ldarg.0
0x948c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9491  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x9496  ldstr    aGeneratetaskba// "GenerateTaskBasedAsynchronousMethod"
0x949b  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x94a0  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id23_Item
0x94a5  ldarg.0
0x94a6  ldarg.0
0x94a7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x94ac  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x94b1  ldstr    aReferencedasse// "ReferencedAssemblies"
0x94b6  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x94bb  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id39_ReferencedAssemblies
0x94c0  ldarg.0
0x94c1  ldarg.0
0x94c2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x94c7  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x94cc  ldstr    aSerializer// "Serializer"
0x94d1  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x94d6  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id35_Serializer
0x94db  ldarg.0
0x94dc  ldarg.0
0x94dd  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x94e2  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x94e7  ldstr    aProtocol_0// "Protocol"
0x94ec  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x94f1  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id21_Protocol
0x94f6  ldarg.0
0x94f7  ldarg.0
0x94f8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x94fd  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x9502  ldstr    aServicecontrac_0// "ServiceContractMapping"
0x9507  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x950c  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id44_ServiceContractMapping
0x9511  ldarg.0
0x9512  ldarg.0
0x9513  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9518  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x951d  ldstr    aName_0// "Name"
0x9522  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x9527  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id14_Name
0x952c  ldarg.0
0x952d  ldarg.0
0x952e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9533  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x9538  ldstr    aSourceurl// "SourceUrl"
0x953d  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x9542  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id19_SourceUrl
0x9547  ldarg.0
0x9548  ldarg.0
0x9549  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x954e  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x9553  ldstr    aCategory// "Category"
0x9558  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x955d  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id51_Category
0x9562  ldarg.0
0x9563  ldarg.0
0x9564  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9569  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x956e  ldstr    asc_3D8E0// ""
0x9573  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x9578  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id5_Item
0x957d  ldarg.0
0x957e  ldarg.0
0x957f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9584  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x9589  ldstr    aNamespacemappi// "NamespaceMappings"
0x958e  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x9593  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id30_NamespaceMappings
0x9598  ldarg.0
0x9599  ldarg.0
0x959a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x959f  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x95a4  ldstr    aMetadata// "Metadata"
0x95a9  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x95ae  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id9_Metadata
0x95b3  ldarg.0
0x95b4  ldarg.0
0x95b5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x95ba  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x95bf  ldstr    aEnabledatabind// "EnableDataBinding"
0x95c4  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
0x95c9  stfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id24_EnableDataBinding
0x95ce  ldarg.0
0x95cf  ldarg.0
0x95d0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x95d5  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlReader::get_NameTable()
0x95da  ldstr    aImportxmltypes// "ImportXmlTypes"
0x95df  callvirt instance string [System.Xml]System.Xml.XmlNameTable::Add(string)
  ... truncated ...
```
