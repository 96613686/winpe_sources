# System.Web.Resources.AtlasWeb::get_JSON_InvalidRecursionLimit

- ea: `0x28f10`
- end: `0x28f25`
- name: `System.Web.Resources.AtlasWeb::get_JSON_InvalidRecursionLimit`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x31d80`

## callees

- `0x28080`

## string_xrefs

- `0x28f15`: `JSON_InvalidRecursionLimit`

## pseudocode

```c

```

## disassembly

```asm
0x28f10  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28f15  ldstr    aJsonInvalidrec// "JSON_InvalidRecursionLimit"
0x28f1a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28f1f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28f24  ret
```
