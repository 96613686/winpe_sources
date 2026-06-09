# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write2_ReferencedType

- ea: `0x6ac0`
- end: `0x6b32`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write2_ReferencedType`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6690`

## callees

- `0x31b0`
- `0x6ac0`

## string_xrefs

- `0x6b0a`: `urn:schemas-microsoft-com:xml-wcfservicemap`

## pseudocode

```c

```

## disassembly

```asm
0x6ac0  ldarg.3
0x6ac1  brtrue.s loc_6AD0
0x6ac3  ldarg.s  4
0x6ac5  brfalse.s loc_6ACF
0x6ac7  ldarg.0
0x6ac8  ldarg.1
0x6ac9  ldarg.2
0x6aca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x6acf  ret
0x6ad0  ldarg.s  5
0x6ad2  brtrue.s loc_6AF5
0x6ad4  ldarg.3
0x6ad5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6ada  stloc.0
0x6adb  ldloc.0
0x6adc  ldtoken  System.Web.Compilation.WCFModel.ReferencedType
0x6ae1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6ae6  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6aeb  brtrue.s loc_6AF5
0x6aed  ldarg.0
0x6aee  ldarg.3
0x6aef  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x6af4  throw
0x6af5  ldarg.0
0x6af6  ldarg.1
0x6af7  ldarg.2
0x6af8  ldarg.3
0x6af9  ldc.i4.0
0x6afa  ldnull
0x6afb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x6b00  ldarg.s  5
0x6b02  brfalse.s loc_6B14
0x6b04  ldarg.0
0x6b05  ldstr    aReferencedtype// "ReferencedType"
0x6b0a  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6b0f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x6b14  ldarg.0
0x6b15  ldstr    aTypename_0// "TypeName"
0x6b1a  ldstr    asc_3D8E0// ""
0x6b1f  ldarg.3
0x6b20  callvirt instance string System.Web.Compilation.WCFModel.ReferencedType::get_TypeName()
0x6b25  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6b2a  ldarg.0
0x6b2b  ldarg.3
0x6b2c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x6b31  ret
```
