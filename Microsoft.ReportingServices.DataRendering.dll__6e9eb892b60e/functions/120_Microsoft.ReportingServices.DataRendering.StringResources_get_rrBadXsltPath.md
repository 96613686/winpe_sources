# Microsoft.ReportingServices.DataRendering.StringResources::get_rrBadXsltPath

- ea: `0x120`
- end: `0x135`
- name: `Microsoft.ReportingServices.DataRendering.StringResources::get_rrBadXsltPath`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7bf0`

## callees

- `0x30`

## string_xrefs

- `0x125`: `rrBadXsltPath`

## pseudocode

```c

```

## disassembly

```asm
0x120  call     class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.DataRendering.StringResources::get_ResourceManager()
0x125  ldstr    aRrbadxsltpath// "rrBadXsltPath"
0x12a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.DataRendering.StringResources::resourceCulture
0x12f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x134  ret
```
