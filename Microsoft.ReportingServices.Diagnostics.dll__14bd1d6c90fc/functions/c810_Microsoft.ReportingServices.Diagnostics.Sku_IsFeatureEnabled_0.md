# Microsoft.ReportingServices.Diagnostics.Sku::IsFeatureEnabled_0

- ea: `0xc810`
- end: `0xc81d`
- name: `Microsoft.ReportingServices.Diagnostics.Sku::IsFeatureEnabled_0`
- size: `13`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x160`
- `0x170`
- `0x1a0`
- `0x5fd0`
- `0xa9e0`
- `0xc7d0`
- `0xc840`

## callees

- `0xc7e0`
- `0xcb00`

## pseudocode

```c

```

## disassembly

```asm
0xc810  ldarg.0
0xc811  call     valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.ReportingServices.Diagnostics.Sku::GetInstalledSku(string instanceId)
0xc816  ldarg.1
0xc817  call     bool Microsoft.ReportingServices.Diagnostics.Sku::IsFeatureEnabled(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType sku, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures feature)
0xc81c  ret
```
