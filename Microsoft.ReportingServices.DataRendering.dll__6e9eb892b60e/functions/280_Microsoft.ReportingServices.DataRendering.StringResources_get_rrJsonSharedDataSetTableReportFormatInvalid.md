# Microsoft.ReportingServices.DataRendering.StringResources::get_rrJsonSharedDataSetTableReportFormatInvalid

- ea: `0x280`
- end: `0x295`
- name: `Microsoft.ReportingServices.DataRendering.StringResources::get_rrJsonSharedDataSetTableReportFormatInvalid`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5e60`
- `0x5fc0`

## callees

- `0x30`

## string_xrefs

- `0x285`: `rrJsonSharedDataSetTableReportFormatInvalid`

## pseudocode

```c

```

## disassembly

```asm
0x280  call     class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.DataRendering.StringResources::get_ResourceManager()
0x285  ldstr    aRrjsonsharedda// "rrJsonSharedDataSetTableReportFormatInv"...
0x28a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.DataRendering.StringResources::resourceCulture
0x28f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x294  ret
```
