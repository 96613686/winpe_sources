# Microsoft.ReportingServices.Diagnostics.Sku::GetInstalledSku

- ea: `0xcb00`
- end: `0xcb11`
- name: `Microsoft.ReportingServices.Diagnostics.Sku::GetInstalledSku`
- size: `17`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180`
- `0x5e20`
- `0xc7c0`
- `0xc810`
- `0xc820`
- `0xc830`
- `0xc860`
- `0xc9e0`
- `0xcb20`

## callees

- `0xcad0`

## pseudocode

```c

```

## disassembly

```asm
0xcb00  ldarg.0
0xcb01  call     void Microsoft.ReportingServices.Diagnostics.Sku::InitializeSkuInfo(string instanceId)
0xcb06  ldsfld   class Microsoft.ReportingServices.Diagnostics.SkuInfo Microsoft.ReportingServices.Diagnostics.Sku::skuInfo
0xcb0b  ldfld    valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.ReportingServices.Diagnostics.SkuInfo::Sku
0xcb10  ret
```
