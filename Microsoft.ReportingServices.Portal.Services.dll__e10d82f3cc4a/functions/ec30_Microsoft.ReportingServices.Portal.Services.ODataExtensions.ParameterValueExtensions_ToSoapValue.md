# Microsoft.ReportingServices.Portal.Services.ODataExtensions.ParameterValueExtensions::ToSoapValue

- ea: `0xec30`
- end: `0xec4b`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.ParameterValueExtensions::ToSoapValue`
- size: `27`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xe8d0`
- `0xe910`
- `0xe9d0`
- `0xeb00`
- `0x21f60`
- `0x21f90`

## callees

- `0xec30`
- `0xec90`
- `0xecb0`

## pseudocode

```c

```

## disassembly

```asm
0xec30  ldarg.0
0xec31  brfalse.s loc_EC49
0xec33  ldarg.1
0xec34  ldc.i4.1
0xec35  bne.un.s loc_EC3E
0xec37  ldarg.0
0xec38  call     string Microsoft.ReportingServices.Portal.Services.ODataExtensions.ParameterValueExtensions::FormatAsGeneralDateShortTime(string Iso8601Date)
0xec3d  ret
0xec3e  ldarg.1
0xec3f  ldc.i4.3
0xec40  bne.un.s loc_EC49
0xec42  ldarg.0
0xec43  call     string Microsoft.ReportingServices.Portal.Services.ODataExtensions.ParameterValueExtensions::FormatAsLocalizedFloat(string invariantFloat)
0xec48  ret
0xec49  ldarg.0
0xec4a  ret
```
