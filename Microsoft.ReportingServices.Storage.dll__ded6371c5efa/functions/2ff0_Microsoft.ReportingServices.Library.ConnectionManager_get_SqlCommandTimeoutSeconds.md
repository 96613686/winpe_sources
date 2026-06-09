# Microsoft.ReportingServices.Library.ConnectionManager::get_SqlCommandTimeoutSeconds

- ea: `0x2ff0`
- end: `0x2ffb`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::get_SqlCommandTimeoutSeconds`
- size: `11`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x11f0`
- `0x17c0`
- `0x20b0`
- `0x35a0`
- `0x3d20`
- `0x6ba0`

## pseudocode

```c

```

## disassembly

```asm
0x2ff0  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x2ff5  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_DBQueryTimeout()
0x2ffa  ret
```
