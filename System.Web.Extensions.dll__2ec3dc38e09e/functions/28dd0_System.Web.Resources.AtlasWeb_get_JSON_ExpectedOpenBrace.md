# System.Web.Resources.AtlasWeb::get_JSON_ExpectedOpenBrace

- ea: `0x28dd0`
- end: `0x28de5`
- name: `System.Web.Resources.AtlasWeb::get_JSON_ExpectedOpenBrace`
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

- `0x28dd5`: `JSON_ExpectedOpenBrace`

## pseudocode

```c

```

## disassembly

```asm
0x28dd0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28dd5  ldstr    aJsonExpectedop// "JSON_ExpectedOpenBrace"
0x28dda  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28ddf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28de4  ret
```
