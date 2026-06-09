# System.Web.Resources.AtlasWeb::get_JSON_InvalidArrayExpectComma

- ea: `0x28e30`
- end: `0x28e45`
- name: `System.Web.Resources.AtlasWeb::get_JSON_InvalidArrayExpectComma`
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

- `0x28e35`: `JSON_InvalidArrayExpectComma`

## pseudocode

```c

```

## disassembly

```asm
0x28e30  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28e35  ldstr    aJsonInvalidarr_0// "JSON_InvalidArrayExpectComma"
0x28e3a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28e3f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28e44  ret
```
