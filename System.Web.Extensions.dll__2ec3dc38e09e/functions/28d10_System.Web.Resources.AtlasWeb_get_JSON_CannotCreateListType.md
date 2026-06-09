# System.Web.Resources.AtlasWeb::get_JSON_CannotCreateListType

- ea: `0x28d10`
- end: `0x28d25`
- name: `System.Web.Resources.AtlasWeb::get_JSON_CannotCreateListType`
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

- `0x28d15`: `JSON_CannotCreateListType`

## pseudocode

```c

```

## disassembly

```asm
0x28d10  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28d15  ldstr    aJsonCannotcrea// "JSON_CannotCreateListType"
0x28d1a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28d1f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28d24  ret
```
