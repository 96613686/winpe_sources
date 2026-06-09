# System.Web.Resources.AtlasWeb::get_JSON_InvalidObject

- ea: `0x28ef0`
- end: `0x28f05`
- name: `System.Web.Resources.AtlasWeb::get_JSON_InvalidObject`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x31170`

## callees

- `0x28080`

## string_xrefs

- `0x28ef5`: `JSON_InvalidObject`

## pseudocode

```c

```

## disassembly

```asm
0x28ef0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28ef5  ldstr    aJsonInvalidobj// "JSON_InvalidObject"
0x28efa  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28eff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28f04  ret
```
