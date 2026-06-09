# System.Web.Resources.AtlasWeb::get_JSON_InvalidMemberName

- ea: `0x28ed0`
- end: `0x28ee5`
- name: `System.Web.Resources.AtlasWeb::get_JSON_InvalidMemberName`
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

- `0x28ed5`: `JSON_InvalidMemberName`

## pseudocode

```c

```

## disassembly

```asm
0x28ed0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28ed5  ldstr    aJsonInvalidmem// "JSON_InvalidMemberName"
0x28eda  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28edf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28ee4  ret
```
