# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write9_ClientOptions

- ea: `0x6690`
- end: `0x6a1f`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write9_ClientOptions`
- size: `911`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6210`

## callees

- `0x1620`
- `0x1650`
- `0x1680`
- `0x1690`
- `0x16b0`
- `0x16d0`
- `0x16f0`
- `0x1710`
- `0x1730`
- `0x1750`
- `0x1770`
- `0x1790`
- `0x17b0`
- `0x17e0`
- `0x17f0`
- `0x1820`
- `0x1830`
- `0x1850`
- `0x1870`
- `0x1890`
- `0x6690`
- `0x6a20`
- `0x6ac0`
- `0x6b40`
- `0x6bc0`
- `0x6c10`
- `0x6cf0`

## string_xrefs

- `0x66da`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x66ea`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x670d`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x6728`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x674d`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x6763`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x678f`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x67aa`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x67c5`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x67ea`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x6801`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x683d`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x6854`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x6886`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x68a1`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x68c5`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x68e8`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x6903`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x692a`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x6941`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x697f`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x6996`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x69d4`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x69eb`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x6708`: `GenerateTaskBasedAsynchronousMethod`
- `0x678a`: `ImportXmlTypes`
- `0x69cf`: `ServiceContractMappings`
- `0x69e6`: `ServiceContractMapping`

## pseudocode

```c

```

## disassembly

```asm
0x6690  ldarg.3
0x6691  brtrue.s loc_66A0
0x6693  ldarg.s  4
0x6695  brfalse.s loc_669F
0x6697  ldarg.0
0x6698  ldarg.1
0x6699  ldarg.2
0x669a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x669f  ret
0x66a0  ldarg.s  5
0x66a2  brtrue.s loc_66C5
0x66a4  ldarg.3
0x66a5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x66aa  stloc.0
0x66ab  ldloc.0
0x66ac  ldtoken  System.Web.Compilation.WCFModel.ClientOptions
0x66b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x66b6  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x66bb  brtrue.s loc_66C5
0x66bd  ldarg.0
0x66be  ldarg.3
0x66bf  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x66c4  throw
0x66c5  ldarg.0
0x66c6  ldarg.1
0x66c7  ldarg.2
0x66c8  ldarg.3
0x66c9  ldc.i4.0
0x66ca  ldnull
0x66cb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x66d0  ldarg.s  5
0x66d2  brfalse.s loc_66E4
0x66d4  ldarg.0
0x66d5  ldstr    aClientoptions// "ClientOptions"
0x66da  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x66df  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x66e4  ldarg.0
0x66e5  ldstr    aGenerateasynch// "GenerateAsynchronousMethods"
0x66ea  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x66ef  ldarg.3
0x66f0  callvirt instance bool System.Web.Compilation.WCFModel.ClientOptions::get_GenerateAsynchronousMethods()
0x66f5  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x66fa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x66ff  ldarg.3
0x6700  callvirt instance bool System.Web.Compilation.WCFModel.ClientOptions::get_GenerateTaskBasedAsynchronousMethodSpecified()
0x6705  brfalse.s loc_6722
0x6707  ldarg.0
0x6708  ldstr    aGeneratetaskba// "GenerateTaskBasedAsynchronousMethod"
0x670d  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6712  ldarg.3
0x6713  callvirt instance bool System.Web.Compilation.WCFModel.ClientOptions::get_GenerateTaskBasedAsynchronousMethod()
0x6718  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x671d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x6722  ldarg.0
0x6723  ldstr    aEnabledatabind// "EnableDataBinding"
0x6728  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x672d  ldarg.3
0x672e  callvirt instance bool System.Web.Compilation.WCFModel.ClientOptions::get_EnableDataBinding()
0x6733  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x6738  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x673d  ldarg.3
0x673e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ReferencedType> System.Web.Compilation.WCFModel.ClientOptions::get_ExcludedTypeList()
0x6743  stloc.1
0x6744  ldloc.1
0x6745  brfalse.s loc_6789
0x6747  ldarg.0
0x6748  ldstr    aExcludedtypes// "ExcludedTypes"
0x674d  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6752  ldnull
0x6753  ldc.i4.0
0x6754  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x6759  ldc.i4.0
0x675a  stloc.2
0x675b  br.s     loc_677A
0x675d  ldarg.0
0x675e  ldstr    aExcludedtype// "ExcludedType"
0x6763  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6768  ldloc.1
0x6769  ldloc.2
0x676a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ReferencedType>::get_Item(!!T0)
0x676f  ldc.i4.1
0x6770  ldc.i4.0
0x6771  call     instance void System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write2_ReferencedType(string n, string ns, class System.Web.Compilation.WCFModel.ReferencedType o, bool isNullable, bool needType)
0x6776  ldloc.2
0x6777  ldc.i4.1
0x6778  add
0x6779  stloc.2
0x677a  ldloc.2
0x677b  ldloc.1
0x677c  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x6781  blt.s    loc_675D
0x6783  ldarg.0
0x6784  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x6789  ldarg.0
0x678a  ldstr    aImportxmltypes// "ImportXmlTypes"
0x678f  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6794  ldarg.3
0x6795  callvirt instance bool System.Web.Compilation.WCFModel.ClientOptions::get_ImportXmlTypes()
0x679a  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x679f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x67a4  ldarg.0
0x67a5  ldstr    aGenerateintern// "GenerateInternalTypes"
0x67aa  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x67af  ldarg.3
0x67b0  callvirt instance bool System.Web.Compilation.WCFModel.ClientOptions::get_GenerateInternalTypes()
0x67b5  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x67ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x67bf  ldarg.0
0x67c0  ldstr    aGeneratemessag// "GenerateMessageContracts"
0x67c5  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x67ca  ldarg.3
0x67cb  callvirt instance bool System.Web.Compilation.WCFModel.ClientOptions::get_GenerateMessageContracts()
0x67d0  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x67d5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x67da  ldarg.3
0x67db  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.NamespaceMapping> System.Web.Compilation.WCFModel.ClientOptions::get_NamespaceMappingList()
0x67e0  stloc.3
0x67e1  ldloc.3
0x67e2  brfalse.s loc_682B
0x67e4  ldarg.0
0x67e5  ldstr    aNamespacemappi// "NamespaceMappings"
0x67ea  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x67ef  ldnull
0x67f0  ldc.i4.0
0x67f1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x67f6  ldc.i4.0
0x67f7  stloc.s  4
0x67f9  br.s     loc_681B
0x67fb  ldarg.0
0x67fc  ldstr    aNamespacemappi_0// "NamespaceMapping"
0x6801  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6806  ldloc.3
0x6807  ldloc.s  4
0x6809  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.NamespaceMapping>::get_Item(!!T0)
0x680e  ldc.i4.1
0x680f  ldc.i4.0
0x6810  call     instance void System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write3_NamespaceMapping(string n, string ns, class System.Web.Compilation.WCFModel.NamespaceMapping o, bool isNullable, bool needType)
0x6815  ldloc.s  4
0x6817  ldc.i4.1
0x6818  add
0x6819  stloc.s  4
0x681b  ldloc.s  4
0x681d  ldloc.3
0x681e  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x6823  blt.s    loc_67FB
0x6825  ldarg.0
0x6826  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x682b  ldarg.3
0x682c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ReferencedCollectionType> System.Web.Compilation.WCFModel.ClientOptions::get_CollectionMappingList()
0x6831  stloc.s  5
0x6833  ldloc.s  5
0x6835  brfalse.s loc_6880
0x6837  ldarg.0
0x6838  ldstr    aCollectionmapp// "CollectionMappings"
0x683d  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6842  ldnull
0x6843  ldc.i4.0
0x6844  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x6849  ldc.i4.0
0x684a  stloc.s  6
0x684c  br.s     loc_686F
0x684e  ldarg.0
0x684f  ldstr    aCollectionmapp_0// "CollectionMapping"
0x6854  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6859  ldloc.s  5
0x685b  ldloc.s  6
0x685d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ReferencedCollectionType>::get_Item(!!T0)
0x6862  ldc.i4.1
0x6863  ldc.i4.0
0x6864  call     instance void System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write5_ReferencedCollectionType(string n, string ns, class System.Web.Compilation.WCFModel.ReferencedCollectionType o, bool isNullable, bool needType)
0x6869  ldloc.s  6
0x686b  ldc.i4.1
0x686c  add
0x686d  stloc.s  6
0x686f  ldloc.s  6
0x6871  ldloc.s  5
0x6873  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x6878  blt.s    loc_684E
0x687a  ldarg.0
0x687b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x6880  ldarg.0
0x6881  ldstr    aGenerateserial// "GenerateSerializableTypes"
0x6886  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x688b  ldarg.3
0x688c  callvirt instance bool System.Web.Compilation.WCFModel.ClientOptions::get_GenerateSerializableTypes()
0x6891  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x6896  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x689b  ldarg.0
0x689c  ldstr    aSerializer// "Serializer"
0x68a1  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x68a6  ldarg.0
0x68a7  ldarg.3
0x68a8  callvirt instance valuetype ProxySerializerType System.Web.Compilation.WCFModel.ClientOptions::get_Serializer()
0x68ad  call     instance string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write6_ProxySerializerType(valuetype ProxySerializerType v)
0x68b2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x68b7  ldarg.3
0x68b8  callvirt instance bool System.Web.Compilation.WCFModel.ClientOptions::get_UseSerializerForFaultsSpecified()
0x68bd  brfalse.s loc_68DA
0x68bf  ldarg.0
0x68c0  ldstr    aUseserializerf// "UseSerializerForFaults"
0x68c5  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x68ca  ldarg.3
0x68cb  callvirt instance bool System.Web.Compilation.WCFModel.ClientOptions::get_UseSerializerForFaults()
0x68d0  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x68d5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x68da  ldarg.3
0x68db  callvirt instance bool System.Web.Compilation.WCFModel.ClientOptions::get_WrappedSpecified()
0x68e0  brfalse.s loc_68FD
0x68e2  ldarg.0
0x68e3  ldstr    aWrapped// "Wrapped"
0x68e8  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x68ed  ldarg.3
0x68ee  callvirt instance bool System.Web.Compilation.WCFModel.ClientOptions::get_Wrapped()
0x68f3  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x68f8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x68fd  ldarg.0
0x68fe  ldstr    aReferenceallas// "ReferenceAllAssemblies"
0x6903  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6908  ldarg.3
0x6909  callvirt instance bool System.Web.Compilation.WCFModel.ClientOptions::get_ReferenceAllAssemblies()
0x690e  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x6913  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x6918  ldarg.3
0x6919  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ReferencedAssembly> System.Web.Compilation.WCFModel.ClientOptions::get_ReferencedAssemblyList()
0x691e  stloc.s  7
0x6920  ldloc.s  7
0x6922  brfalse.s loc_696D
0x6924  ldarg.0
0x6925  ldstr    aReferencedasse// "ReferencedAssemblies"
0x692a  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x692f  ldnull
0x6930  ldc.i4.0
0x6931  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x6936  ldc.i4.0
0x6937  stloc.s  8
0x6939  br.s     loc_695C
0x693b  ldarg.0
0x693c  ldstr    aReferencedasse_0// "ReferencedAssembly"
0x6941  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6946  ldloc.s  7
0x6948  ldloc.s  8
0x694a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ReferencedAssembly>::get_Item(!!T0)
0x694f  ldc.i4.1
0x6950  ldc.i4.0
0x6951  call     instance void System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write7_ReferencedAssembly(string n, string ns, class System.Web.Compilation.WCFModel.ReferencedAssembly o, bool isNullable, bool needType)
0x6956  ldloc.s  8
0x6958  ldc.i4.1
0x6959  add
0x695a  stloc.s  8
0x695c  ldloc.s  8
0x695e  ldloc.s  7
0x6960  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x6965  blt.s    loc_693B
0x6967  ldarg.0
0x6968  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x696d  ldarg.3
0x696e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ReferencedType> System.Web.Compilation.WCFModel.ClientOptions::get_ReferencedDataContractTypeList()
0x6973  stloc.s  9
0x6975  ldloc.s  9
0x6977  brfalse.s loc_69C2
0x6979  ldarg.0
0x697a  ldstr    aReferenceddata// "ReferencedDataContractTypes"
0x697f  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6984  ldnull
0x6985  ldc.i4.0
0x6986  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x698b  ldc.i4.0
0x698c  stloc.s  0xA
0x698e  br.s     loc_69B1
0x6990  ldarg.0
0x6991  ldstr    aReferenceddata_0// "ReferencedDataContractType"
0x6996  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x699b  ldloc.s  9
0x699d  ldloc.s  0xA
0x699f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ReferencedType>::get_Item(!!T0)
0x69a4  ldc.i4.1
0x69a5  ldc.i4.0
0x69a6  call     instance void System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write2_ReferencedType(string n, string ns, class System.Web.Compilation.WCFModel.ReferencedType o, bool isNullable, bool needType)
0x69ab  ldloc.s  0xA
0x69ad  ldc.i4.1
0x69ae  add
0x69af  stloc.s  0xA
0x69b1  ldloc.s  0xA
0x69b3  ldloc.s  9
0x69b5  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x69ba  blt.s    loc_6990
0x69bc  ldarg.0
0x69bd  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x69c2  ldarg.3
0x69c3  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ContractMapping> System.Web.Compilation.WCFModel.ClientOptions::get_ServiceContractMappingList()
0x69c8  stloc.s  0xB
0x69ca  ldloc.s  0xB
0x69cc  brfalse.s loc_6A17
0x69ce  ldarg.0
0x69cf  ldstr    aServicecontrac// "ServiceContractMappings"
0x69d4  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x69d9  ldnull
0x69da  ldc.i4.0
0x69db  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x69e0  ldc.i4.0
  ... truncated ...
```
