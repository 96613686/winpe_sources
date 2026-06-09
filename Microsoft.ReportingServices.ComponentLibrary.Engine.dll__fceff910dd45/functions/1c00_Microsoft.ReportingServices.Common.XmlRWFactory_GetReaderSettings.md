# Microsoft.ReportingServices.Common.XmlRWFactory::GetReaderSettings

- ea: `0x1c00`
- end: `0x1c0d`
- name: `Microsoft.ReportingServices.Common.XmlRWFactory::GetReaderSettings`
- size: `13`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1bd0`
- `0x1be0`

## pseudocode

```c

```

## disassembly

```asm
0x1c00  newobj   instance void [System.Xml]System.Xml.XmlReaderSettings::.ctor()
0x1c05  dup
0x1c06  ldc.i4.0
0x1c07  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_CheckCharacters(bool)
0x1c0c  ret
```
