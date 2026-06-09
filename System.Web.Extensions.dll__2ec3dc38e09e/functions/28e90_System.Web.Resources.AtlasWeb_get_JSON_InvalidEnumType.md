# System.Web.Resources.AtlasWeb::get_JSON_InvalidEnumType

- ea: `0x28e90`
- end: `0x28ea5`
- name: `System.Web.Resources.AtlasWeb::get_JSON_InvalidEnumType`
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

- `0x28e95`: `JSON_InvalidEnumType`

## pseudocode

```c

```

## disassembly

```asm
0x28e90  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28e95  ldstr    aJsonInvalidenu// "JSON_InvalidEnumType"
0x28e9a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28e9f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28ea4  ret
```
