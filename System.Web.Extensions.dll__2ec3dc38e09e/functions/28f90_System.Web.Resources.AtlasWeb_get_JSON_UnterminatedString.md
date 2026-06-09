# System.Web.Resources.AtlasWeb::get_JSON_UnterminatedString

- ea: `0x28f90`
- end: `0x28fa5`
- name: `System.Web.Resources.AtlasWeb::get_JSON_UnterminatedString`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x31610`

## callees

- `0x28080`

## string_xrefs

- `0x28f95`: `JSON_UnterminatedString`

## pseudocode

```c

```

## disassembly

```asm
0x28f90  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28f95  ldstr    aJsonUnterminat// "JSON_UnterminatedString"
0x28f9a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28f9f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28fa4  ret
```
