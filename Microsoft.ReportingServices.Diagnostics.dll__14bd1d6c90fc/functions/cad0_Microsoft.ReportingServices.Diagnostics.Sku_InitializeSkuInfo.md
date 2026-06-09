# Microsoft.ReportingServices.Diagnostics.Sku::InitializeSkuInfo

- ea: `0xcad0`
- end: `0xcae3`
- name: `Microsoft.ReportingServices.Diagnostics.Sku::InitializeSkuInfo`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xcaf0`
- `0xcb00`

## callees

- `0xca60`
- `0xcad0`

## pseudocode

```c

```

## disassembly

```asm
0xcad0  ldsfld   class Microsoft.ReportingServices.Diagnostics.SkuInfo Microsoft.ReportingServices.Diagnostics.Sku::skuInfo
0xcad5  brtrue.s loc_CAE2
0xcad7  ldarg.0
0xcad8  call     class Microsoft.ReportingServices.Diagnostics.SkuInfo Microsoft.ReportingServices.Diagnostics.Sku::GetSkuInfoForInstance(string instanceId)
0xcadd  stsfld   class Microsoft.ReportingServices.Diagnostics.SkuInfo Microsoft.ReportingServices.Diagnostics.Sku::skuInfo
0xcae2  ret
```
