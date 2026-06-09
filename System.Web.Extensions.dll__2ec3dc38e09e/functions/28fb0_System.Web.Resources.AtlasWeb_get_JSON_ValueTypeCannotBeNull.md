# System.Web.Resources.AtlasWeb::get_JSON_ValueTypeCannotBeNull

- ea: `0x28fb0`
- end: `0x28fc5`
- name: `System.Web.Resources.AtlasWeb::get_JSON_ValueTypeCannotBeNull`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x32dc0`

## callees

- `0x28080`

## string_xrefs

- `0x28fb5`: `JSON_ValueTypeCannotBeNull`

## pseudocode

```c

```

## disassembly

```asm
0x28fb0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28fb5  ldstr    aJsonValuetypec// "JSON_ValueTypeCannotBeNull"
0x28fba  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28fbf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28fc4  ret
```
