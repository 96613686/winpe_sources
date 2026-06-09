# Microsoft.ReportingServices.Common.XmlFragmentUtil::CreateXmlWriterSettings

- ea: `0x1c80`
- end: `0x1c8d`
- name: `Microsoft.ReportingServices.Common.XmlFragmentUtil::CreateXmlWriterSettings`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1c90`

## callees

- `0x1c10`

## pseudocode

```c

```

## disassembly

```asm
0x1c80  call     class [System.Xml]System.Xml.XmlWriterSettings Microsoft.ReportingServices.Common.XmlRWFactory::GetWriterSettings()
0x1c85  dup
0x1c86  ldc.i4.1
0x1c87  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x1c8c  ret
```
