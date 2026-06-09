# Microsoft.ReportingServices.DataRendering.StringResources::get_rrJsonRenderOutputNotSupported

- ea: `0x260`
- end: `0x275`
- name: `Microsoft.ReportingServices.DataRendering.StringResources::get_rrJsonRenderOutputNotSupported`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5aa0`

## callees

- `0x30`

## string_xrefs

- `0x265`: `rrJsonRenderOutputNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x260  call     class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.DataRendering.StringResources::get_ResourceManager()
0x265  ldstr    aRrjsonrenderou// "rrJsonRenderOutputNotSupported"
0x26a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.DataRendering.StringResources::resourceCulture
0x26f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x274  ret
```
