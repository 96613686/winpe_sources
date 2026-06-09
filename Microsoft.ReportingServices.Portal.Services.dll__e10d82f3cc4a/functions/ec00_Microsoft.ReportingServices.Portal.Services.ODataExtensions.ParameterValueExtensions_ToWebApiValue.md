# Microsoft.ReportingServices.Portal.Services.ODataExtensions.ParameterValueExtensions::ToWebApiValue

- ea: `0xec00`
- end: `0xec27`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.ParameterValueExtensions::ToWebApiValue`
- size: `39`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xeb40`
- `0xebc0`
- `0xf7a0`
- `0x21f30`

## callees

- `0xec00`
- `0xec50`
- `0xecd0`

## pseudocode

```c

```

## disassembly

```asm
0xec00  ldarg.0
0xec01  brfalse.s loc_EC25
0xec03  ldarg.1
0xec04  ldc.i4.1
0xec05  bne.un.s loc_EC0F
0xec07  ldarg.0
0xec08  ldarg.2
0xec09  call     string Microsoft.ReportingServices.Portal.Services.ODataExtensions.ParameterValueExtensions::FormatAsISO8601Date(string date, [opt] string culture)
0xec0e  ret
0xec0f  ldarg.1
0xec10  brtrue.s loc_EC19
0xec12  ldarg.0
0xec13  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0xec18  ret
0xec19  ldarg.1
0xec1a  ldc.i4.3
0xec1b  bne.un.s loc_EC25
0xec1d  ldarg.0
0xec1e  ldarg.2
0xec1f  call     string Microsoft.ReportingServices.Portal.Services.ODataExtensions.ParameterValueExtensions::FormatAsInvariantFloat(string localizedFloat, string culture)
0xec24  ret
0xec25  ldarg.0
0xec26  ret
```
