# Microsoft.ReportingServices.Diagnostics.Localization::CatalogCultureCompare

- ea: `0x3a20`
- end: `0x3a2d`
- name: `Microsoft.ReportingServices.Diagnostics.Localization::CatalogCultureCompare`
- size: `13`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8310`
- `0x8350`
- `0x8410`
- `0x8c50`
- `0x8c70`
- `0x8f20`
- `0x9350`
- `0xca60`

## callees

- `0x3a30`

## pseudocode

```c

```

## disassembly

```asm
0x3a20  ldarg.0
0x3a21  ldarg.1
0x3a22  call     valuetype [mscorlib]System.StringComparison Microsoft.ReportingServices.Diagnostics.Localization::get_CatalogStringComparison()
0x3a27  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x3a2c  ret
```
