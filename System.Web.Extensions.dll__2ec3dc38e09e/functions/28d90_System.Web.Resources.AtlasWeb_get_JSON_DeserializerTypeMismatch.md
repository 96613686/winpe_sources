# System.Web.Resources.AtlasWeb::get_JSON_DeserializerTypeMismatch

- ea: `0x28d90`
- end: `0x28da5`
- name: `System.Web.Resources.AtlasWeb::get_JSON_DeserializerTypeMismatch`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x32ae0`

## callees

- `0x28080`

## string_xrefs

- `0x28d95`: `JSON_DeserializerTypeMismatch`

## pseudocode

```c

```

## disassembly

```asm
0x28d90  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28d95  ldstr    aJsonDeserializ// "JSON_DeserializerTypeMismatch"
0x28d9a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28d9f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28da4  ret
```
