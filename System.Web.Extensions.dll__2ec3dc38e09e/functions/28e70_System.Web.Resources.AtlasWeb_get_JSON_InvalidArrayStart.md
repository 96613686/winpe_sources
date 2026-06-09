# System.Web.Resources.AtlasWeb::get_JSON_InvalidArrayStart

- ea: `0x28e70`
- end: `0x28e85`
- name: `System.Web.Resources.AtlasWeb::get_JSON_InvalidArrayStart`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x30f70`

## callees

- `0x28080`

## string_xrefs

- `0x28e75`: `JSON_InvalidArrayStart`

## pseudocode

```c

```

## disassembly

```asm
0x28e70  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28e75  ldstr    aJsonInvalidarr_2// "JSON_InvalidArrayStart"
0x28e7a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28e7f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28e84  ret
```
