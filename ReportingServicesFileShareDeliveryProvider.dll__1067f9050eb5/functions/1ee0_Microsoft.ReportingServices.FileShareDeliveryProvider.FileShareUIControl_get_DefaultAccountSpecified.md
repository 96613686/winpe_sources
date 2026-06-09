# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_DefaultAccountSpecified

- ea: `0x1ee0`
- end: `0x1eeb`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::get_DefaultAccountSpecified`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3390`

## pseudocode

```c

```

## disassembly

```asm
0x1ee0  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x1ee5  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_IsFileShareAccountPresent()
0x1eea  ret
```
