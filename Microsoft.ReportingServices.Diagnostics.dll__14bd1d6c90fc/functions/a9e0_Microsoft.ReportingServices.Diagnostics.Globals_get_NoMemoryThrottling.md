# Microsoft.ReportingServices.Diagnostics.Globals::get_NoMemoryThrottling

- ea: `0xa9e0`
- end: `0xa9f2`
- name: `Microsoft.ReportingServices.Diagnostics.Globals::get_NoMemoryThrottling`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xb110`

## callees

- `0x33c0`
- `0xa930`
- `0xc810`

## pseudocode

```c

```

## disassembly

```asm
0xa9e0  call     class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0xa9e5  callvirt instance string Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0xa9ea  ldc.i4.s 0x13
0xa9ec  call     bool Microsoft.ReportingServices.Diagnostics.Sku::IsFeatureEnabled(string instanceId, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures feature)
0xa9f1  ret
```
