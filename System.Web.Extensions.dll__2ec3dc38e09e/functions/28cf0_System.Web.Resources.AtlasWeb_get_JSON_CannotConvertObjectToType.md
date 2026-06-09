# System.Web.Resources.AtlasWeb::get_JSON_CannotConvertObjectToType

- ea: `0x28cf0`
- end: `0x28d05`
- name: `System.Web.Resources.AtlasWeb::get_JSON_CannotConvertObjectToType`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x32e30`

## callees

- `0x28080`

## string_xrefs

- `0x28cf5`: `JSON_CannotConvertObjectToType`

## pseudocode

```c

```

## disassembly

```asm
0x28cf0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28cf5  ldstr    aJsonCannotconv// "JSON_CannotConvertObjectToType"
0x28cfa  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28cff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28d04  ret
```
