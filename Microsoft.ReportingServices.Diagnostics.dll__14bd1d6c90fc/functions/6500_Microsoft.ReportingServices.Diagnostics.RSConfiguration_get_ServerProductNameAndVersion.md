# Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ServerProductNameAndVersion

- ea: `0x6500`
- end: `0x652d`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ServerProductNameAndVersion`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2e0`
- `0x6530`

## callees

- `0x6480`
- `0x64c0`
- `0x6500`
- `0xc9e0`

## pseudocode

```c

```

## disassembly

```asm
0x6500  ldarg.0
0x6501  call     instance string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ServerProductVersion()
0x6506  brtrue.s loc_650E
0x6508  call     string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ServerProductName()
0x650d  ret
0x650e  call     bool Microsoft.ReportingServices.Diagnostics.Sku::IsBiServer()
0x6513  brtrue.s loc_6521
0x6515  ldarg.0
0x6516  call     instance string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ServerProductVersion()
0x651b  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStringsWrapper::ProductNameSSRSAndVersion(string)
0x6520  ret
0x6521  ldarg.0
0x6522  call     instance string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ServerProductVersion()
0x6527  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStringsWrapper::ProductNamePBIRSAndVersion(string)
0x652c  ret
```
