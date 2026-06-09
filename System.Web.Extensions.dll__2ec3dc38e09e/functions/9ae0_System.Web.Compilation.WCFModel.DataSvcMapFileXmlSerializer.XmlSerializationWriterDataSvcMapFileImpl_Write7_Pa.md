# System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write7_Parameter

- ea: `0x9ae0`
- end: `0x9b68`
- name: `System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write7_Parameter`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x9920`

## callees

- `0x2e90`
- `0x2eb0`
- `0x9ae0`

## string_xrefs

- `0x9b2a`: `urn:schemas-microsoft-com:xml-dataservicemap`

## pseudocode

```c

```

## disassembly

```asm
0x9ae0  ldarg.3
0x9ae1  brtrue.s loc_9AF0
0x9ae3  ldarg.s  4
0x9ae5  brfalse.s loc_9AEF
0x9ae7  ldarg.0
0x9ae8  ldarg.1
0x9ae9  ldarg.2
0x9aea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x9aef  ret
0x9af0  ldarg.s  5
0x9af2  brtrue.s loc_9B15
0x9af4  ldarg.3
0x9af5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x9afa  stloc.0
0x9afb  ldloc.0
0x9afc  ldtoken  System.Web.Compilation.WCFModel.Parameter
0x9b01  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9b06  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9b0b  brtrue.s loc_9B15
0x9b0d  ldarg.0
0x9b0e  ldarg.3
0x9b0f  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x9b14  throw
0x9b15  ldarg.0
0x9b16  ldarg.1
0x9b17  ldarg.2
0x9b18  ldarg.3
0x9b19  ldc.i4.0
0x9b1a  ldnull
0x9b1b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x9b20  ldarg.s  5
0x9b22  brfalse.s loc_9B34
0x9b24  ldarg.0
0x9b25  ldstr    aParameter// "Parameter"
0x9b2a  ldstr    aUrnSchemasMicr_11// "urn:schemas-microsoft-com:xml-dataservi"...
0x9b2f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x9b34  ldarg.0
0x9b35  ldstr    aName_0// "Name"
0x9b3a  ldstr    asc_3D8E0// ""
0x9b3f  ldarg.3
0x9b40  callvirt instance string System.Web.Compilation.WCFModel.Parameter::get_Name()
0x9b45  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x9b4a  ldarg.0
0x9b4b  ldstr    aValue_0// "Value"
0x9b50  ldstr    asc_3D8E0// ""
0x9b55  ldarg.3
0x9b56  callvirt instance string System.Web.Compilation.WCFModel.Parameter::get_Value()
0x9b5b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x9b60  ldarg.0
0x9b61  ldarg.3
0x9b62  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x9b67  ret
```
