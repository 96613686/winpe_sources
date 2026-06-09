# Microsoft.ReportingServices.DataRendering.StringResources::get_LocalizedXmlRendererName

- ea: `0xe0`
- end: `0xf5`
- name: `Microsoft.ReportingServices.DataRendering.StringResources::get_LocalizedXmlRendererName`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7870`

## callees

- `0x30`

## string_xrefs

- `0xe5`: `LocalizedXmlRendererName`

## pseudocode

```c

```

## disassembly

```asm
0xe0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.DataRendering.StringResources::get_ResourceManager()
0xe5  ldstr    aLocalizedxmlre// "LocalizedXmlRendererName"
0xea  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.DataRendering.StringResources::resourceCulture
0xef  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xf4  ret
```
