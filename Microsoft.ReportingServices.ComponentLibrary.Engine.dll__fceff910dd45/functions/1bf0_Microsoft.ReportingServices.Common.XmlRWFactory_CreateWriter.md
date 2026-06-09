# Microsoft.ReportingServices.Common.XmlRWFactory::CreateWriter

- ea: `0x1bf0`
- end: `0x1bfc`
- name: `Microsoft.ReportingServices.Common.XmlRWFactory::CreateWriter`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1c10`

## pseudocode

```c

```

## disassembly

```asm
0x1bf0  ldarg.0
0x1bf1  call     class [System.Xml]System.Xml.XmlWriterSettings Microsoft.ReportingServices.Common.XmlRWFactory::GetWriterSettings()
0x1bf6  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.Stream, class [System.Xml]System.Xml.XmlWriterSettings)
0x1bfb  ret
```
