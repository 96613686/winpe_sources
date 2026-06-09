# System.Web.Resources.AtlasWeb::get_JSON_InvalidMaxJsonLength

- ea: `0x28eb0`
- end: `0x28ec5`
- name: `System.Web.Resources.AtlasWeb::get_JSON_InvalidMaxJsonLength`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x31d50`

## callees

- `0x28080`

## string_xrefs

- `0x28eb5`: `JSON_InvalidMaxJsonLength`

## pseudocode

```c

```

## disassembly

```asm
0x28eb0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28eb5  ldstr    aJsonInvalidmax// "JSON_InvalidMaxJsonLength"
0x28eba  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28ebf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28ec4  ret
```
