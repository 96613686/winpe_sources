# Microsoft.ReportingServices.Common.XmlRWFactory::GetWriterSettings

- ea: `0x1c10`
- end: `0x1c1d`
- name: `Microsoft.ReportingServices.Common.XmlRWFactory::GetWriterSettings`
- size: `13`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1bf0`
- `0x1c80`

## pseudocode

```c

```

## disassembly

```asm
0x1c10  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x1c15  dup
0x1c16  ldc.i4.0
0x1c17  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_CheckCharacters(bool)
0x1c1c  ret
```
