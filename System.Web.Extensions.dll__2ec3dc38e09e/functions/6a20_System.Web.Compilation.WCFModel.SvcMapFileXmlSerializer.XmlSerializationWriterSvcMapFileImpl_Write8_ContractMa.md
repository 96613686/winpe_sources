# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write8_ContractMapping

- ea: `0x6a20`
- end: `0x6abe`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write8_ContractMapping`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6690`

## callees

- `0x18d0`
- `0x18f0`
- `0x1910`
- `0x6a20`

## string_xrefs

- `0x6a6a`: `urn:schemas-microsoft-com:xml-wcfservicemap`

## pseudocode

```c

```

## disassembly

```asm
0x6a20  ldarg.3
0x6a21  brtrue.s loc_6A30
0x6a23  ldarg.s  4
0x6a25  brfalse.s loc_6A2F
0x6a27  ldarg.0
0x6a28  ldarg.1
0x6a29  ldarg.2
0x6a2a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x6a2f  ret
0x6a30  ldarg.s  5
0x6a32  brtrue.s loc_6A55
0x6a34  ldarg.3
0x6a35  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6a3a  stloc.0
0x6a3b  ldloc.0
0x6a3c  ldtoken  System.Web.Compilation.WCFModel.ContractMapping
0x6a41  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6a46  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6a4b  brtrue.s loc_6A55
0x6a4d  ldarg.0
0x6a4e  ldarg.3
0x6a4f  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x6a54  throw
0x6a55  ldarg.0
0x6a56  ldarg.1
0x6a57  ldarg.2
0x6a58  ldarg.3
0x6a59  ldc.i4.0
0x6a5a  ldnull
0x6a5b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x6a60  ldarg.s  5
0x6a62  brfalse.s loc_6A74
0x6a64  ldarg.0
0x6a65  ldstr    aContractmappin// "ContractMapping"
0x6a6a  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6a6f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x6a74  ldarg.0
0x6a75  ldstr    aName_0// "Name"
0x6a7a  ldstr    asc_3D8E0// ""
0x6a7f  ldarg.3
0x6a80  callvirt instance string System.Web.Compilation.WCFModel.ContractMapping::get_Name()
0x6a85  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6a8a  ldarg.0
0x6a8b  ldstr    aTargetnamespac// "TargetNamespace"
0x6a90  ldstr    asc_3D8E0// ""
0x6a95  ldarg.3
0x6a96  callvirt instance string System.Web.Compilation.WCFModel.ContractMapping::get_TargetNamespace()
0x6a9b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6aa0  ldarg.0
0x6aa1  ldstr    aTypename_0// "TypeName"
0x6aa6  ldstr    asc_3D8E0// ""
0x6aab  ldarg.3
0x6aac  callvirt instance string System.Web.Compilation.WCFModel.ContractMapping::get_TypeName()
0x6ab1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6ab6  ldarg.0
0x6ab7  ldarg.3
0x6ab8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x6abd  ret
```
