# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write14_ExtensionFile

- ea: `0x6390`
- end: `0x6418`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write14_ExtensionFile`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x6210`

## callees

- `0x1ca0`
- `0x1d40`
- `0x6390`

## string_xrefs

- `0x63da`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x63d5`: `ExtensionFile`

## pseudocode

```c

```

## disassembly

```asm
0x6390  ldarg.3
0x6391  brtrue.s loc_63A0
0x6393  ldarg.s  4
0x6395  brfalse.s loc_639F
0x6397  ldarg.0
0x6398  ldarg.1
0x6399  ldarg.2
0x639a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x639f  ret
0x63a0  ldarg.s  5
0x63a2  brtrue.s loc_63C5
0x63a4  ldarg.3
0x63a5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x63aa  stloc.0
0x63ab  ldloc.0
0x63ac  ldtoken  System.Web.Compilation.WCFModel.ExtensionFile
0x63b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x63b6  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x63bb  brtrue.s loc_63C5
0x63bd  ldarg.0
0x63be  ldarg.3
0x63bf  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x63c4  throw
0x63c5  ldarg.0
0x63c6  ldarg.1
0x63c7  ldarg.2
0x63c8  ldarg.3
0x63c9  ldc.i4.0
0x63ca  ldnull
0x63cb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x63d0  ldarg.s  5
0x63d2  brfalse.s loc_63E4
0x63d4  ldarg.0
0x63d5  ldstr    aExtensionfile// "ExtensionFile"
0x63da  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x63df  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x63e4  ldarg.0
0x63e5  ldstr    aFilename_0// "FileName"
0x63ea  ldstr    asc_3D8E0// ""
0x63ef  ldarg.3
0x63f0  callvirt instance string System.Web.Compilation.WCFModel.ExternalFile::get_FileName()
0x63f5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x63fa  ldarg.0
0x63fb  ldstr    aName_0// "Name"
0x6400  ldstr    asc_3D8E0// ""
0x6405  ldarg.3
0x6406  callvirt instance string System.Web.Compilation.WCFModel.ExtensionFile::get_Name()
0x640b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6410  ldarg.0
0x6411  ldarg.3
0x6412  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x6417  ret
```
