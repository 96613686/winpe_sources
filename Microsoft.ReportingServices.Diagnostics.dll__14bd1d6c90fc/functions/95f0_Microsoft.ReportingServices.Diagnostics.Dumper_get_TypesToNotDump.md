# Microsoft.ReportingServices.Diagnostics.Dumper::get_TypesToNotDump

- ea: `0x95f0`
- end: `0x95fb`
- name: `Microsoft.ReportingServices.Diagnostics.Dumper::get_TypesToNotDump`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9980`
- `0x9b10`

## callees

- `0x3440`
- `0xa930`

## pseudocode

```c

```

## disassembly

```asm
0x95f0  call     class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x95f5  callvirt instance class [System]System.Collections.Specialized.StringCollection Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_WatsonDumpExcludeIfContainsExceptions()
0x95fa  ret
```
