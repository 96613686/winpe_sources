# System.Web.Resources.AtlasWeb::get_JSON_InvalidArrayEnd

- ea: `0x28e10`
- end: `0x28e25`
- name: `System.Web.Resources.AtlasWeb::get_JSON_InvalidArrayEnd`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x30f70`

## callees

- `0x28080`

## string_xrefs

- `0x28e15`: `JSON_InvalidArrayEnd`

## pseudocode

```c

```

## disassembly

```asm
0x28e10  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28e15  ldstr    aJsonInvalidarr// "JSON_InvalidArrayEnd"
0x28e1a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x28e1f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28e24  ret
```
