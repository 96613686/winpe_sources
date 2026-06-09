# System.Web.Resources.AtlasWeb::get_JSON_StringNotQuoted

- ea: `0x28f70`
- end: `0x28f85`
- name: `System.Web.Resources.AtlasWeb::get_JSON_StringNotQuoted`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x319b0`

## callees

- `0x28080`

## string_xrefs

- `0x28f75`: `JSON_StringNotQuoted`

## pseudocode

```c

```

## disassembly

```asm
0x28f70  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28f75  ldstr    aJsonStringnotq// "JSON_StringNotQuoted"
0x28f7a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28f7f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28f84  ret
```
