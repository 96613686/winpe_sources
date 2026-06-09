# System.Web.Resources.AtlasWeb::get_Common_GreaterThanOrEqualToZeroAndLessThanOrEqualToOne

- ea: `0x282b0`
- end: `0x282c5`
- name: `System.Web.Resources.AtlasWeb::get_Common_GreaterThanOrEqualToZeroAndLessThanOrEqualToOne`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x28080`

## string_xrefs

- `0x282b5`: `Common_GreaterThanOrEqualToZeroAndLessThanOrEqualToOne`

## pseudocode

```c

```

## disassembly

```asm
0x282b0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x282b5  ldstr    aCommonGreatert_0// "Common_GreaterThanOrEqualToZeroAndLessT"...
0x282ba  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x282bf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x282c4  ret
```
