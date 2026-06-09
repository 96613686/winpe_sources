# Microsoft.ReportingServices.Modeling.SRErrors::Xml_NodeMismatch

- ea: `0x24360`
- end: `0x2437d`
- name: `Microsoft.ReportingServices.Modeling.SRErrors::Xml_NodeMismatch`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xae40`
- `0xbaa0`

## callees

- `0x38f30`

## string_xrefs

- `0x24360`: `Xml_NodeMismatch`

## pseudocode

```c

```

## disassembly

```asm
0x24360  ldstr    aXmlNodemismatc// "Xml_NodeMismatch"
0x24365  ldarg.0
0x24366  box      [System.Xml]System.Xml.XmlNodeType
0x2436b  ldarg.1
0x2436c  ldarg.2
0x2436d  ldarg.3
0x2436e  box      [System.Xml]System.Xml.XmlNodeType
0x24373  ldarg.s  4
0x24375  ldarg.s  5
0x24377  call     string Keys::GetString(string key, object arg0, object arg1, object arg2, object arg3, object arg4, object arg5)
0x2437c  ret
```
