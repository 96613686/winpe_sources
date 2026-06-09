# System.Web.Resources.AtlasWeb::get_DynamicControlBase_ConvertEmptyStringToNull

- ea: `0x28530`
- end: `0x28545`
- name: `System.Web.Resources.AtlasWeb::get_DynamicControlBase_ConvertEmptyStringToNull`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x28080`

## string_xrefs

- `0x28535`: `DynamicControlBase_ConvertEmptyStringToNull`

## pseudocode

```c

```

## disassembly

```asm
0x28530  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28535  ldstr    aDynamiccontrol// "DynamicControlBase_ConvertEmptyStringTo"...
0x2853a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2853f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28544  ret
```
