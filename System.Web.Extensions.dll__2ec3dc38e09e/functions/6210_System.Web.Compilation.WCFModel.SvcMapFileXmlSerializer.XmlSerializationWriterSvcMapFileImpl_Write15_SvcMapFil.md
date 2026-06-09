# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write15_SvcMapFileImpl

- ea: `0x6210`
- end: `0x638c`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write15_SvcMapFileImpl`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x61d0`

## callees

- `0x3e90`
- `0x3ee0`
- `0x3f20`
- `0x3f40`
- `0x3f60`
- `0x6210`
- `0x6390`
- `0x6420`
- `0x65e0`
- `0x6690`

## string_xrefs

- `0x625a`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x6280`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x62a2`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x62b8`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x62ee`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x6305`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x6341`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x6358`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x633c`: `Extensions`
- `0x6353`: `ExtensionFile`

## pseudocode

```c

```

## disassembly

```asm
0x6210  ldarg.3
0x6211  brtrue.s loc_6220
0x6213  ldarg.s  4
0x6215  brfalse.s loc_621F
0x6217  ldarg.0
0x6218  ldarg.1
0x6219  ldarg.2
0x621a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x621f  ret
0x6220  ldarg.s  5
0x6222  brtrue.s loc_6245
0x6224  ldarg.3
0x6225  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x622a  stloc.0
0x622b  ldloc.0
0x622c  ldtoken  System.Web.Compilation.WCFModel.SvcMapFileImpl
0x6231  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6236  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x623b  brtrue.s loc_6245
0x623d  ldarg.0
0x623e  ldarg.3
0x623f  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x6244  throw
0x6245  ldarg.0
0x6246  ldarg.1
0x6247  ldarg.2
0x6248  ldarg.3
0x6249  ldc.i4.0
0x624a  ldnull
0x624b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x6250  ldarg.s  5
0x6252  brfalse.s loc_6264
0x6254  ldarg.0
0x6255  ldstr    aSvcmapfileimpl// "SvcMapFileImpl"
0x625a  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x625f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x6264  ldarg.0
0x6265  ldstr    aId// "ID"
0x626a  ldstr    asc_3D8E0// ""
0x626f  ldarg.3
0x6270  callvirt instance string System.Web.Compilation.WCFModel.SvcMapFileImpl::get_ID()
0x6275  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x627a  ldarg.0
0x627b  ldstr    aClientoptions// "ClientOptions"
0x6280  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6285  ldarg.3
0x6286  callvirt instance class System.Web.Compilation.WCFModel.ClientOptions System.Web.Compilation.WCFModel.SvcMapFileImpl::get_ClientOptions()
0x628b  ldc.i4.0
0x628c  ldc.i4.0
0x628d  call     instance void System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write9_ClientOptions(string n, string ns, class System.Web.Compilation.WCFModel.ClientOptions o, bool isNullable, bool needType)
0x6292  ldarg.3
0x6293  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataSource> System.Web.Compilation.WCFModel.SvcMapFileImpl::get_MetadataSourceList()
0x6298  stloc.1
0x6299  ldloc.1
0x629a  brfalse.s loc_62DE
0x629c  ldarg.0
0x629d  ldstr    aMetadatasource// "MetadataSources"
0x62a2  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x62a7  ldnull
0x62a8  ldc.i4.0
0x62a9  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x62ae  ldc.i4.0
0x62af  stloc.2
0x62b0  br.s     loc_62CF
0x62b2  ldarg.0
0x62b3  ldstr    aMetadatasource_0// "MetadataSource"
0x62b8  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x62bd  ldloc.1
0x62be  ldloc.2
0x62bf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataSource>::get_Item(!!T0)
0x62c4  ldc.i4.1
0x62c5  ldc.i4.0
0x62c6  call     instance void System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write10_MetadataSource(string n, string ns, class System.Web.Compilation.WCFModel.MetadataSource o, bool isNullable, bool needType)
0x62cb  ldloc.2
0x62cc  ldc.i4.1
0x62cd  add
0x62ce  stloc.2
0x62cf  ldloc.2
0x62d0  ldloc.1
0x62d1  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x62d6  blt.s    loc_62B2
0x62d8  ldarg.0
0x62d9  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x62de  ldarg.3
0x62df  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataFile> System.Web.Compilation.WCFModel.SvcMapFileImpl::get_MetadataList()
0x62e4  stloc.3
0x62e5  ldloc.3
0x62e6  brfalse.s loc_632F
0x62e8  ldarg.0
0x62e9  ldstr    aMetadata// "Metadata"
0x62ee  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x62f3  ldnull
0x62f4  ldc.i4.0
0x62f5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x62fa  ldc.i4.0
0x62fb  stloc.s  4
0x62fd  br.s     loc_631F
0x62ff  ldarg.0
0x6300  ldstr    aMetadatafile// "MetadataFile"
0x6305  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x630a  ldloc.3
0x630b  ldloc.s  4
0x630d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.MetadataFile>::get_Item(!!T0)
0x6312  ldc.i4.1
0x6313  ldc.i4.0
0x6314  call     instance void System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write13_MetadataFile(string n, string ns, class System.Web.Compilation.WCFModel.MetadataFile o, bool isNullable, bool needType)
0x6319  ldloc.s  4
0x631b  ldc.i4.1
0x631c  add
0x631d  stloc.s  4
0x631f  ldloc.s  4
0x6321  ldloc.3
0x6322  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x6327  blt.s    loc_62FF
0x6329  ldarg.0
0x632a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x632f  ldarg.3
0x6330  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ExtensionFile> System.Web.Compilation.WCFModel.SvcMapFileImpl::get_Extensions()
0x6335  stloc.s  5
0x6337  ldloc.s  5
0x6339  brfalse.s loc_6384
0x633b  ldarg.0
0x633c  ldstr    aExtensions// "Extensions"
0x6341  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6346  ldnull
0x6347  ldc.i4.0
0x6348  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x634d  ldc.i4.0
0x634e  stloc.s  6
0x6350  br.s     loc_6373
0x6352  ldarg.0
0x6353  ldstr    aExtensionfile// "ExtensionFile"
0x6358  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x635d  ldloc.s  5
0x635f  ldloc.s  6
0x6361  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.Web.Compilation.WCFModel.ExtensionFile>::get_Item(!!T0)
0x6366  ldc.i4.1
0x6367  ldc.i4.0
0x6368  call     instance void System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write14_ExtensionFile(string n, string ns, class System.Web.Compilation.WCFModel.ExtensionFile o, bool isNullable, bool needType)
0x636d  ldloc.s  6
0x636f  ldc.i4.1
0x6370  add
0x6371  stloc.s  6
0x6373  ldloc.s  6
0x6375  ldloc.s  5
0x6377  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x637c  blt.s    loc_6352
0x637e  ldarg.0
0x637f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x6384  ldarg.0
0x6385  ldarg.3
0x6386  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x638b  ret
```
