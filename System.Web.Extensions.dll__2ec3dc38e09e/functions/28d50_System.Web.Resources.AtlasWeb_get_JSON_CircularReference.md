# System.Web.Resources.AtlasWeb::get_JSON_CircularReference

- ea: `0x28d50`
- end: `0x28d65`
- name: `System.Web.Resources.AtlasWeb::get_JSON_CircularReference`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x32430`

## callees

- `0x28080`

## string_xrefs

- `0x28d55`: `JSON_CircularReference`

## pseudocode

```c

```

## disassembly

```asm
0x28d50  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28d55  ldstr    aJsonCircularre// "JSON_CircularReference"
0x28d5a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28d5f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28d64  ret
```
