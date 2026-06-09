# System.Web.Resources.AtlasWeb::get_Common_ArgumentInvalidType

- ea: `0x28270`
- end: `0x28285`
- name: `System.Web.Resources.AtlasWeb::get_Common_ArgumentInvalidType`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x137a0`
- `0x13880`

## callees

- `0x28080`

## string_xrefs

- `0x28275`: `Common_ArgumentInvalidType`

## pseudocode

```c

```

## disassembly

```asm
0x28270  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28275  ldstr    aCommonArgument// "Common_ArgumentInvalidType"
0x2827a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2827f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28284  ret
```
