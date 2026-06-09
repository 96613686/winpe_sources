# Microsoft.ReportingServices.Common.XmlRWFactory::CreateReader

- ea: `0x1bd0`
- end: `0x1bdc`
- name: `Microsoft.ReportingServices.Common.XmlRWFactory::CreateReader`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1c00`

## pseudocode

```c

```

## disassembly

```asm
0x1bd0  ldarg.0
0x1bd1  call     class [System.Xml]System.Xml.XmlReaderSettings Microsoft.ReportingServices.Common.XmlRWFactory::GetReaderSettings()
0x1bd6  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.Stream, class [System.Xml]System.Xml.XmlReaderSettings)
0x1bdb  ret
```
