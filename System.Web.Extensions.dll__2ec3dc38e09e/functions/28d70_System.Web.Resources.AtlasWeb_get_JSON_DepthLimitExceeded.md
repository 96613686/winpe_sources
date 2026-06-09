# System.Web.Resources.AtlasWeb::get_JSON_DepthLimitExceeded

- ea: `0x28d70`
- end: `0x28d85`
- name: `System.Web.Resources.AtlasWeb::get_JSON_DepthLimitExceeded`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x30ec0`
- `0x323a0`

## callees

- `0x28080`

## string_xrefs

- `0x28d75`: `JSON_DepthLimitExceeded`

## pseudocode

```c

```

## disassembly

```asm
0x28d70  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28d75  ldstr    aJsonDepthlimit// "JSON_DepthLimitExceeded"
0x28d7a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28d7f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28d84  ret
```
