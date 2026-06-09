# System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write6_ExtensionFile

- ea: `0x9b70`
- end: `0x9bf8`
- name: `System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write6_ExtensionFile`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x9920`

## callees

- `0x1ca0`
- `0x1d40`
- `0x9b70`

## string_xrefs

- `0x9bb5`: `ExtensionFile`
- `0x9bba`: `urn:schemas-microsoft-com:xml-dataservicemap`

## pseudocode

```c

```

## disassembly

```asm
0x9b70  ldarg.3
0x9b71  brtrue.s loc_9B80
0x9b73  ldarg.s  4
0x9b75  brfalse.s loc_9B7F
0x9b77  ldarg.0
0x9b78  ldarg.1
0x9b79  ldarg.2
0x9b7a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x9b7f  ret
0x9b80  ldarg.s  5
0x9b82  brtrue.s loc_9BA5
0x9b84  ldarg.3
0x9b85  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x9b8a  stloc.0
0x9b8b  ldloc.0
0x9b8c  ldtoken  System.Web.Compilation.WCFModel.ExtensionFile
0x9b91  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9b96  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9b9b  brtrue.s loc_9BA5
0x9b9d  ldarg.0
0x9b9e  ldarg.3
0x9b9f  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x9ba4  throw
0x9ba5  ldarg.0
0x9ba6  ldarg.1
0x9ba7  ldarg.2
0x9ba8  ldarg.3
0x9ba9  ldc.i4.0
0x9baa  ldnull
0x9bab  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x9bb0  ldarg.s  5
0x9bb2  brfalse.s loc_9BC4
0x9bb4  ldarg.0
0x9bb5  ldstr    aExtensionfile// "ExtensionFile"
0x9bba  ldstr    aUrnSchemasMicr_11// "urn:schemas-microsoft-com:xml-dataservi"...
0x9bbf  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x9bc4  ldarg.0
0x9bc5  ldstr    aFilename_0// "FileName"
0x9bca  ldstr    asc_3D8E0// ""
0x9bcf  ldarg.3
0x9bd0  callvirt instance string System.Web.Compilation.WCFModel.ExternalFile::get_FileName()
0x9bd5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x9bda  ldarg.0
0x9bdb  ldstr    aName_0// "Name"
0x9be0  ldstr    asc_3D8E0// ""
0x9be5  ldarg.3
0x9be6  callvirt instance string System.Web.Compilation.WCFModel.ExtensionFile::get_Name()
0x9beb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x9bf0  ldarg.0
0x9bf1  ldarg.3
0x9bf2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x9bf7  ret
```
