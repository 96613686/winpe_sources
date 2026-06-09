# System.Web.Resources.AtlasWeb::get_JSON_NoConstructor

- ea: `0x28f50`
- end: `0x28f65`
- name: `System.Web.Resources.AtlasWeb::get_JSON_NoConstructor`
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

- `0x28f55`: `JSON_NoConstructor`

## pseudocode

```c

```

## disassembly

```asm
0x28f50  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28f55  ldstr    aJsonNoconstruc// "JSON_NoConstructor"
0x28f5a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28f5f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28f64  ret
```
