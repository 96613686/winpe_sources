# System.Web.Resources.AtlasWeb::get_JSON_DictionaryTypeNotSupported

- ea: `0x28db0`
- end: `0x28dc5`
- name: `System.Web.Resources.AtlasWeb::get_JSON_DictionaryTypeNotSupported`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x32200`
- `0x32ae0`

## callees

- `0x28080`

## string_xrefs

- `0x28db5`: `JSON_DictionaryTypeNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x28db0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28db5  ldstr    aJsonDictionary// "JSON_DictionaryTypeNotSupported"
0x28dba  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28dbf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28dc4  ret
```
