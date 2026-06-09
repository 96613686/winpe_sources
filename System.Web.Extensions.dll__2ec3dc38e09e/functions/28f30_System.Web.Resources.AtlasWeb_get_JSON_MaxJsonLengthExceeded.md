# System.Web.Resources.AtlasWeb::get_JSON_MaxJsonLengthExceeded

- ea: `0x28f30`
- end: `0x28f45`
- name: `System.Web.Resources.AtlasWeb::get_JSON_MaxJsonLengthExceeded`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x31cc0`
- `0x31f40`

## callees

- `0x28080`

## string_xrefs

- `0x28f35`: `JSON_MaxJsonLengthExceeded`

## pseudocode

```c

```

## disassembly

```asm
0x28f30  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28f35  ldstr    aJsonMaxjsonlen// "JSON_MaxJsonLengthExceeded"
0x28f3a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28f3f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28f44  ret
```
