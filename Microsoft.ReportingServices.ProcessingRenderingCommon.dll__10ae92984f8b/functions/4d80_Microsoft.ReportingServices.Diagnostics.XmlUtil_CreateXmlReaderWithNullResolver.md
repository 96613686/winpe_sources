# Microsoft.ReportingServices.Diagnostics.XmlUtil::CreateXmlReaderWithNullResolver

- ea: `0x4d80`
- end: `0x4d9a`
- name: `Microsoft.ReportingServices.Diagnostics.XmlUtil::CreateXmlReaderWithNullResolver`
- size: `26`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4cc0`
- `0x4ce0`
- `0x4cf0`
- `0x4d10`
- `0x4d30`
- `0x4d40`
- `0x4d60`

## pseudocode

```c

```

## disassembly

```asm
0x4d80  ldarg.0
0x4d81  newobj   instance void [System.Xml]System.Xml.XmlReaderSettings::.ctor()
0x4d86  dup
0x4d87  ldnull
0x4d88  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x4d8d  dup
0x4d8e  ldc.i4.0
0x4d8f  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_DtdProcessing(valuetype [System.Xml]System.Xml.DtdProcessing)
0x4d94  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader, class [System.Xml]System.Xml.XmlReaderSettings)
0x4d99  ret
```
