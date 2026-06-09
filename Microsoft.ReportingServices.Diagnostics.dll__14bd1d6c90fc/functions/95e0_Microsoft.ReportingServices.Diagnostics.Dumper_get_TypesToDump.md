# Microsoft.ReportingServices.Diagnostics.Dumper::get_TypesToDump

- ea: `0x95e0`
- end: `0x95eb`
- name: `Microsoft.ReportingServices.Diagnostics.Dumper::get_TypesToDump`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9920`
- `0x9b10`

## callees

- `0x3430`
- `0xa930`

## pseudocode

```c

```

## disassembly

```asm
0x95e0  call     class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x95e5  callvirt instance class [System]System.Collections.Specialized.StringCollection Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_WatsonDumpOnExceptions()
0x95ea  ret
```
