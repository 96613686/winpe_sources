# System.Web.Resources.AtlasWeb::get_JSON_ArrayTypeNotSupported

- ea: `0x28cb0`
- end: `0x28cc5`
- name: `System.Web.Resources.AtlasWeb::get_JSON_ArrayTypeNotSupported`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x32f80`

## callees

- `0x28080`

## string_xrefs

- `0x28cb5`: `JSON_ArrayTypeNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x28cb0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28cb5  ldstr    aJsonArraytypen// "JSON_ArrayTypeNotSupported"
0x28cba  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28cbf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28cc4  ret
```
