# Microsoft.ReportingServices.Diagnostics.Localization::get_FallbackUICulture

- ea: `0x3950`
- end: `0x396d`
- name: `Microsoft.ReportingServices.Diagnostics.Localization::get_FallbackUICulture`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x3810`
- `0x38d0`

## callees

- `0x3910`
- `0x3950`
- `0x3a00`
- `0x3ba0`

## pseudocode

```c

```

## disassembly

```asm
0x3950  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Diagnostics.Localization::get_DefaultReportServerCulture()
0x3955  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x395a  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Diagnostics.Localization::InstalledCulture(string locale)
0x395f  stloc.0
0x3960  ldloc.0
0x3961  brtrue.s loc_396B
0x3963  ldc.i4.s 9
0x3965  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Diagnostics.Localization::GetCultureInfoNoUserOverrides(int32 lcid)
0x396a  ret
0x396b  ldloc.0
0x396c  ret
```
