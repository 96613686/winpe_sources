# Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ServerProductName

- ea: `0x64c0`
- end: `0x64d3`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ServerProductName`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6500`
- `0xfe40`

## callees

- `0x64c0`
- `0x64e0`
- `0x64f0`
- `0xc9e0`

## pseudocode

```c

```

## disassembly

```asm
0x64c0  call     bool Microsoft.ReportingServices.Diagnostics.Sku::IsBiServer()
0x64c5  brtrue.s loc_64CD
0x64c7  call     string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ProductNameSSRS()
0x64cc  ret
0x64cd  call     string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ProductNamePBIRS()
0x64d2  ret
```
