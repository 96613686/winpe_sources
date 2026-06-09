# Microsoft.ReportingServices.DataRendering.StringResources::get_LocalizedSharedDataSetJsonDataRendererName

- ea: `0xc0`
- end: `0xd5`
- name: `Microsoft.ReportingServices.DataRendering.StringResources::get_LocalizedSharedDataSetJsonDataRendererName`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5bc0`

## callees

- `0x30`

## string_xrefs

- `0xc5`: `LocalizedSharedDataSetJsonDataRendererName`

## pseudocode

```c

```

## disassembly

```asm
0xc0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.DataRendering.StringResources::get_ResourceManager()
0xc5  ldstr    aLocalizedshare// "LocalizedSharedDataSetJsonDataRendererN"...
0xca  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.DataRendering.StringResources::resourceCulture
0xcf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xd4  ret
```
