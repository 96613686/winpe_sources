# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write16_ReferenceGroup

- ea: `0x61d0`
- end: `0x6209`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write16_ReferenceGroup`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x9760`

## callees

- `0x61d0`
- `0x6210`

## string_xrefs

- `0x61df`: `urn:schemas-microsoft-com:xml-wcfservicemap`
- `0x61f6`: `urn:schemas-microsoft-com:xml-wcfservicemap`

## pseudocode

```c

```

## disassembly

```asm
0x61d0  ldarg.0
0x61d1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartDocument()
0x61d6  ldarg.1
0x61d7  brtrue.s loc_61EA
0x61d9  ldarg.0
0x61da  ldstr    aReferencegroup// "ReferenceGroup"
0x61df  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x61e4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x61e9  ret
0x61ea  ldarg.0
0x61eb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::TopLevelElement()
0x61f0  ldarg.0
0x61f1  ldstr    aReferencegroup// "ReferenceGroup"
0x61f6  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x61fb  ldarg.1
0x61fc  castclass System.Web.Compilation.WCFModel.SvcMapFileImpl
0x6201  ldc.i4.1
0x6202  ldc.i4.0
0x6203  call     instance void System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write15_SvcMapFileImpl(string n, string ns, class System.Web.Compilation.WCFModel.SvcMapFileImpl o, bool isNullable, bool needType)
0x6208  ret
```
