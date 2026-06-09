# System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write8_DataSvcMapFileImpl

- ea: `0x9920`
- end: `0x9ad9`
- name: `System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write8_DataSvcMapFileImpl`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x98e0`

## callees

- `0x1a00`
- `0x1a50`
- `0x1a70`
- `0x1a90`
- `0x1ab0`
- `0x9920`
- `0x9ae0`
- `0x9b70`
- `0x9c00`
- `0x9dc0`

## string_xrefs

- `0x9a34`: `Extensions`
- `0x9a4b`: `ExtensionFile`
- `0x996a`: `urn:schemas-microsoft-com:xml-dataservicemap`
- `0x999a`: `urn:schemas-microsoft-com:xml-dataservicemap`
- `0x99b0`: `urn:schemas-microsoft-com:xml-dataservicemap`
- `0x99e6`: `urn:schemas-microsoft-com:xml-dataservicemap`
- `0x99fd`: `urn:schemas-microsoft-com:xml-dataservicemap`
- `0x9a39`: `urn:schemas-microsoft-com:xml-dataservicemap`
- `0x9a50`: `urn:schemas-microsoft-com:xml-dataservicemap`
- `0x9a8e`: `urn:schemas-microsoft-com:xml-dataservicemap`
- `0x9aa5`: `urn:schemas-microsoft-com:xml-dataservicemap`

## pseudocode

```c

```

## disassembly

```asm
0x9920  ldarg.3
0x9921  brtrue.s loc_9930
0x9923  ldarg.s  4
0x9925  brfalse.s loc_992F
0x9927  ldarg.0
0x9928  ldarg.1
0x9929  ldarg.2
0x992a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x992f  ret
0x9930  ldarg.s  5
0x9932  brtrue.s loc_9955
0x9934  ldarg.3
0x9935  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x993a  stloc.0
0x993b  ldloc.0
0x993c  ldtoken  System.Web.Compilation.WCFModel.DataSvcMapFileImpl
0x9941  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9946  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x994b  brtrue.s loc_9955
0x994d  ldarg.0
0x994e  ldarg.3
0x994f  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x9954  throw
0x9955  ldarg.0
0x9956  ldarg.1
0x9957  ldarg.2
0x9958  ldarg.3
0x9959  ldc.i4.0
0x995a  ldnull
0x995b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x9960  ldarg.s  5
0x9962  brfalse.s loc_9974
0x9964  ldarg.0
0x9965  ldstr    aDatasvcmapfile// "DataSvcMapFileImpl"
0x996a  ldstr    aUrnSchemasMicr_11// "urn:schemas-microsoft-com:xml-dataservi"...
0x996f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x9974  ldarg.0
0x9975  ldstr    aId// "ID"
0x997a  ldstr    asc_3D8E0// ""
0x997f  ldarg.3
0x9980  callvirt instance string System.Web.Compilation.WCFModel.DataSvcMapFileImpl::get_ID()
0x9985  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x998a  ldarg.3
0x998b  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataSource> System.Web.Compilation.WCFModel.DataSvcMapFileImpl::get_MetadataSourceList()
0x9990  stloc.1
0x9991  ldloc.1
0x9992  brfalse.s loc_99D6
0x9994  ldarg.0
0x9995  ldstr    aMetadatasource// "MetadataSources"
0x999a  ldstr    aUrnSchemasMicr_11// "urn:schemas-microsoft-com:xml-dataservi"...
0x999f  ldnull
0x99a0  ldc.i4.0
0x99a1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x99a6  ldc.i4.0
0x99a7  stloc.2
0x99a8  br.s     loc_99C7
0x99aa  ldarg.0
0x99ab  ldstr    aMetadatasource_0// "MetadataSource"
0x99b0  ldstr    aUrnSchemasMicr_11// "urn:schemas-microsoft-com:xml-dataservi"...
0x99b5  ldloc.1
0x99b6  ldloc.2
0x99b7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataSource>::get_Item(!!T0)
0x99bc  ldc.i4.1
0x99bd  ldc.i4.0
0x99be  call     instance void System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write2_MetadataSource(string n, string ns, class System.Web.Compilation.WCFModel.MetadataSource o, bool isNullable, bool needType)
0x99c3  ldloc.2
0x99c4  ldc.i4.1
0x99c5  add
0x99c6  stloc.2
0x99c7  ldloc.2
0x99c8  ldloc.1
0x99c9  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x99ce  blt.s    loc_99AA
0x99d0  ldarg.0
0x99d1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x99d6  ldarg.3
0x99d7  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataFile> System.Web.Compilation.WCFModel.DataSvcMapFileImpl::get_MetadataList()
0x99dc  stloc.3
0x99dd  ldloc.3
0x99de  brfalse.s loc_9A27
0x99e0  ldarg.0
0x99e1  ldstr    aMetadata// "Metadata"
0x99e6  ldstr    aUrnSchemasMicr_11// "urn:schemas-microsoft-com:xml-dataservi"...
0x99eb  ldnull
0x99ec  ldc.i4.0
0x99ed  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x99f2  ldc.i4.0
0x99f3  stloc.s  4
0x99f5  br.s     loc_9A17
0x99f7  ldarg.0
0x99f8  ldstr    aMetadatafile// "MetadataFile"
0x99fd  ldstr    aUrnSchemasMicr_11// "urn:schemas-microsoft-com:xml-dataservi"...
0x9a02  ldloc.3
0x9a03  ldloc.s  4
0x9a05  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataFile>::get_Item(!!T0)
0x9a0a  ldc.i4.1
0x9a0b  ldc.i4.0
0x9a0c  call     instance void System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write5_MetadataFile(string n, string ns, class System.Web.Compilation.WCFModel.MetadataFile o, bool isNullable, bool needType)
0x9a11  ldloc.s  4
0x9a13  ldc.i4.1
0x9a14  add
0x9a15  stloc.s  4
0x9a17  ldloc.s  4
0x9a19  ldloc.3
0x9a1a  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x9a1f  blt.s    loc_99F7
0x9a21  ldarg.0
0x9a22  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x9a27  ldarg.3
0x9a28  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ExtensionFile> System.Web.Compilation.WCFModel.DataSvcMapFileImpl::get_Extensions()
0x9a2d  stloc.s  5
0x9a2f  ldloc.s  5
0x9a31  brfalse.s loc_9A7C
0x9a33  ldarg.0
0x9a34  ldstr    aExtensions// "Extensions"
0x9a39  ldstr    aUrnSchemasMicr_11// "urn:schemas-microsoft-com:xml-dataservi"...
0x9a3e  ldnull
0x9a3f  ldc.i4.0
0x9a40  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x9a45  ldc.i4.0
0x9a46  stloc.s  6
0x9a48  br.s     loc_9A6B
0x9a4a  ldarg.0
0x9a4b  ldstr    aExtensionfile// "ExtensionFile"
0x9a50  ldstr    aUrnSchemasMicr_11// "urn:schemas-microsoft-com:xml-dataservi"...
0x9a55  ldloc.s  5
0x9a57  ldloc.s  6
0x9a59  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ExtensionFile>::get_Item(!!T0)
0x9a5e  ldc.i4.1
0x9a5f  ldc.i4.0
0x9a60  call     instance void System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write6_ExtensionFile(string n, string ns, class System.Web.Compilation.WCFModel.ExtensionFile o, bool isNullable, bool needType)
0x9a65  ldloc.s  6
0x9a67  ldc.i4.1
0x9a68  add
0x9a69  stloc.s  6
0x9a6b  ldloc.s  6
0x9a6d  ldloc.s  5
0x9a6f  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x9a74  blt.s    loc_9A4A
0x9a76  ldarg.0
0x9a77  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x9a7c  ldarg.3
0x9a7d  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.Parameter> System.Web.Compilation.WCFModel.DataSvcMapFileImpl::get_Parameters()
0x9a82  stloc.s  7
0x9a84  ldloc.s  7
0x9a86  brfalse.s loc_9AD1
0x9a88  ldarg.0
0x9a89  ldstr    aParameters// "Parameters"
0x9a8e  ldstr    aUrnSchemasMicr_11// "urn:schemas-microsoft-com:xml-dataservi"...
0x9a93  ldnull
0x9a94  ldc.i4.0
0x9a95  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x9a9a  ldc.i4.0
0x9a9b  stloc.s  8
0x9a9d  br.s     loc_9AC0
0x9a9f  ldarg.0
0x9aa0  ldstr    aParameter// "Parameter"
0x9aa5  ldstr    aUrnSchemasMicr_11// "urn:schemas-microsoft-com:xml-dataservi"...
0x9aaa  ldloc.s  7
0x9aac  ldloc.s  8
0x9aae  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.Parameter>::get_Item(!!T0)
0x9ab3  ldc.i4.1
0x9ab4  ldc.i4.0
0x9ab5  call     instance void System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write7_Parameter(string n, string ns, class System.Web.Compilation.WCFModel.Parameter o, bool isNullable, bool needType)
0x9aba  ldloc.s  8
0x9abc  ldc.i4.1
0x9abd  add
0x9abe  stloc.s  8
0x9ac0  ldloc.s  8
0x9ac2  ldloc.s  7
0x9ac4  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x9ac9  blt.s    loc_9A9F
0x9acb  ldarg.0
0x9acc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x9ad1  ldarg.0
0x9ad2  ldarg.3
0x9ad3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x9ad8  ret
```
