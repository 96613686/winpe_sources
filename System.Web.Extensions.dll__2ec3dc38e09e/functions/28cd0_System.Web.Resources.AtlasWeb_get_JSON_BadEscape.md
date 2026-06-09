# System.Web.Resources.AtlasWeb::get_JSON_BadEscape

- ea: `0x28cd0`
- end: `0x28ce5`
- name: `System.Web.Resources.AtlasWeb::get_JSON_BadEscape`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x31720`

## callees

- `0x28080`

## string_xrefs

- `0x28cd5`: `JSON_BadEscape`

## pseudocode

```c

```

## disassembly

```asm
0x28cd0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28cd5  ldstr    aJsonBadescape// "JSON_BadEscape"
0x28cda  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28cdf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28ce4  ret
```
