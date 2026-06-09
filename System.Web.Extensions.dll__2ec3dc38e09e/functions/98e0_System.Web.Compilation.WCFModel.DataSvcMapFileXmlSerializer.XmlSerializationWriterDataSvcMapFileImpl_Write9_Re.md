# System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write9_ReferenceGroup

- ea: `0x98e0`
- end: `0x9919`
- name: `System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write9_ReferenceGroup`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb2a0`

## callees

- `0x98e0`
- `0x9920`

## string_xrefs

- `0x98ef`: `urn:schemas-microsoft-com:xml-dataservicemap`
- `0x9906`: `urn:schemas-microsoft-com:xml-dataservicemap`

## pseudocode

```c

```

## disassembly

```asm
0x98e0  ldarg.0
0x98e1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartDocument()
0x98e6  ldarg.1
0x98e7  brtrue.s loc_98FA
0x98e9  ldarg.0
0x98ea  ldstr    aReferencegroup// "ReferenceGroup"
0x98ef  ldstr    aUrnSchemasMicr_11// "urn:schemas-microsoft-com:xml-dataservi"...
0x98f4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x98f9  ret
0x98fa  ldarg.0
0x98fb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::TopLevelElement()
0x9900  ldarg.0
0x9901  ldstr    aReferencegroup// "ReferenceGroup"
0x9906  ldstr    aUrnSchemasMicr_11// "urn:schemas-microsoft-com:xml-dataservi"...
0x990b  ldarg.1
0x990c  castclass System.Web.Compilation.WCFModel.DataSvcMapFileImpl
0x9911  ldc.i4.1
0x9912  ldc.i4.0
0x9913  call     instance void System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write8_DataSvcMapFileImpl(string n, string ns, class System.Web.Compilation.WCFModel.DataSvcMapFileImpl o, bool isNullable, bool needType)
0x9918  ret
```
