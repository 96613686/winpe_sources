# Microsoft.ReportingServices.Diagnostics.Localization::GetCultureInfoNoUserOverrides

- ea: `0x39e0`
- end: `0x39f1`
- name: `Microsoft.ReportingServices.Diagnostics.Localization::GetCultureInfoNoUserOverrides`
- size: `17`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3810`
- `0x3930`
- `0x3970`
- `0x39c0`
- `0x3ba0`

## callees

- `0x3a00`

## pseudocode

```c

```

## disassembly

```asm
0x39e0  ldarg.0
0x39e1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::CreateSpecificCulture(string)
0x39e6  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x39eb  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Diagnostics.Localization::GetCultureInfoNoUserOverrides(int32 lcid)
0x39f0  ret
```
