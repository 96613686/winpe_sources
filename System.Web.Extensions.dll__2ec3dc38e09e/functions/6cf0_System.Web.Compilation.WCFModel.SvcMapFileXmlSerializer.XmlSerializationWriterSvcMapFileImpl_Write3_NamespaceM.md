# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write3_NamespaceMapping

- ea: `0x6cf0`
- end: `0x6d78`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write3_NamespaceMapping`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6690`

## callees

- `0x2e10`
- `0x2e30`
- `0x6cf0`

## string_xrefs

- `0x6d3a`: `urn:schemas-microsoft-com:xml-wcfservicemap`

## pseudocode

```c

```

## disassembly

```asm
0x6cf0  ldarg.3
0x6cf1  brtrue.s loc_6D00
0x6cf3  ldarg.s  4
0x6cf5  brfalse.s loc_6CFF
0x6cf7  ldarg.0
0x6cf8  ldarg.1
0x6cf9  ldarg.2
0x6cfa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x6cff  ret
0x6d00  ldarg.s  5
0x6d02  brtrue.s loc_6D25
0x6d04  ldarg.3
0x6d05  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6d0a  stloc.0
0x6d0b  ldloc.0
0x6d0c  ldtoken  System.Web.Compilation.WCFModel.NamespaceMapping
0x6d11  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6d16  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6d1b  brtrue.s loc_6D25
0x6d1d  ldarg.0
0x6d1e  ldarg.3
0x6d1f  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x6d24  throw
0x6d25  ldarg.0
0x6d26  ldarg.1
0x6d27  ldarg.2
0x6d28  ldarg.3
0x6d29  ldc.i4.0
0x6d2a  ldnull
0x6d2b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x6d30  ldarg.s  5
0x6d32  brfalse.s loc_6D44
0x6d34  ldarg.0
0x6d35  ldstr    aNamespacemappi_0// "NamespaceMapping"
0x6d3a  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6d3f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x6d44  ldarg.0
0x6d45  ldstr    aTargetnamespac// "TargetNamespace"
0x6d4a  ldstr    asc_3D8E0// ""
0x6d4f  ldarg.3
0x6d50  callvirt instance string System.Web.Compilation.WCFModel.NamespaceMapping::get_TargetNamespace()
0x6d55  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6d5a  ldarg.0
0x6d5b  ldstr    aClrnamespace// "ClrNamespace"
0x6d60  ldstr    asc_3D8E0// ""
0x6d65  ldarg.3
0x6d66  callvirt instance string System.Web.Compilation.WCFModel.NamespaceMapping::get_ClrNamespace()
0x6d6b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6d70  ldarg.0
0x6d71  ldarg.3
0x6d72  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x6d77  ret
```
