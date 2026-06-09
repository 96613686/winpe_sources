# Microsoft.ReportingServices.Common.XmlRWFactory::CreateReader_0

- ea: `0x1be0`
- end: `0x1bec`
- name: `Microsoft.ReportingServices.Common.XmlRWFactory::CreateReader_0`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1c30`

## callees

- `0x1c00`

## pseudocode

```c

```

## disassembly

```asm
0x1be0  ldarg.0
0x1be1  call     class [System.Xml]System.Xml.XmlReaderSettings Microsoft.ReportingServices.Common.XmlRWFactory::GetReaderSettings()
0x1be6  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader, class [System.Xml]System.Xml.XmlReaderSettings)
0x1beb  ret
```
