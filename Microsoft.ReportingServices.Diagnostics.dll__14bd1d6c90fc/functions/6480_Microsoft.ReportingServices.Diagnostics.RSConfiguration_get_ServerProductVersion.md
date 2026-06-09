# Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ServerProductVersion

- ea: `0x6480`
- end: `0x6497`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ServerProductVersion`
- size: `23`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2f0`
- `0x6500`
- `0xfe40`

## callees

- `0x6480`
- `0x6560`

## pseudocode

```c

```

## disassembly

```asm
0x6480  ldsfld   string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_ProductVersion
0x6485  brtrue.s loc_6491
0x6487  call     string Microsoft.ReportingServices.Diagnostics.RSConfiguration::GetProductVersion()
0x648c  stsfld   string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_ProductVersion
0x6491  ldsfld   string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_ProductVersion
0x6496  ret
```
