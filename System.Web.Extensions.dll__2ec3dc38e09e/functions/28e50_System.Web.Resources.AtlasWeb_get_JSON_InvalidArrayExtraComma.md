# System.Web.Resources.AtlasWeb::get_JSON_InvalidArrayExtraComma

- ea: `0x28e50`
- end: `0x28e65`
- name: `System.Web.Resources.AtlasWeb::get_JSON_InvalidArrayExtraComma`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x30f70`

## callees

- `0x28080`

## string_xrefs

- `0x28e55`: `JSON_InvalidArrayExtraComma`

## pseudocode

```c

```

## disassembly

```asm
0x28e50  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28e55  ldstr    aJsonInvalidarr_1// "JSON_InvalidArrayExtraComma"
0x28e5a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28e5f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28e64  ret
```
