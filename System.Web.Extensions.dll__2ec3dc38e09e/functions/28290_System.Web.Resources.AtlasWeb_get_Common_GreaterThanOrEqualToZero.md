# System.Web.Resources.AtlasWeb::get_Common_GreaterThanOrEqualToZero

- ea: `0x28290`
- end: `0x282a5`
- name: `System.Web.Resources.AtlasWeb::get_Common_GreaterThanOrEqualToZero`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x28080`

## string_xrefs

- `0x28295`: `Common_GreaterThanOrEqualToZero`

## pseudocode

```c

```

## disassembly

```asm
0x28290  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28295  ldstr    aCommonGreatert// "Common_GreaterThanOrEqualToZero"
0x2829a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2829f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x282a4  ret
```
