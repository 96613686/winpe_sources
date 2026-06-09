# Microsoft.ReportingServices.Common.XmlFragmentUtil::.cctor

- ea: `0x1c90`
- end: `0x1c9b`
- name: `Microsoft.ReportingServices.Common.XmlFragmentUtil::.cctor`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1c80`

## pseudocode

```c

```

## disassembly

```asm
0x1c90  call     class [System.Xml]System.Xml.XmlWriterSettings Microsoft.ReportingServices.Common.XmlFragmentUtil::CreateXmlWriterSettings()
0x1c95  stsfld   class [System.Xml]System.Xml.XmlWriterSettings Microsoft.ReportingServices.Common.XmlFragmentUtil::m_xmlWriterSettings
0x1c9a  ret
```
