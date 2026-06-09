# Microsoft.ReportingServices.Common.XmlFragmentUtil::ReadXmlString

- ea: `0x1c30`
- end: `0x1c3c`
- name: `Microsoft.ReportingServices.Common.XmlFragmentUtil::ReadXmlString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1be0`

## pseudocode

```c

```

## disassembly

```asm
0x1c30  ldarg.0
0x1c31  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x1c36  call     class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Common.XmlRWFactory::CreateReader(class [mscorlib]System.IO.StringReader stringReader)
0x1c3b  ret
```
