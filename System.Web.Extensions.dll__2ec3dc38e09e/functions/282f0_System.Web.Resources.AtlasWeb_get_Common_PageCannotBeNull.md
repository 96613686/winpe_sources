# System.Web.Resources.AtlasWeb::get_Common_PageCannotBeNull

- ea: `0x282f0`
- end: `0x28305`
- name: `System.Web.Resources.AtlasWeb::get_Common_PageCannotBeNull`
- size: `21`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xf540`
- `0x10330`
- `0x10360`
- `0x11fc0`
- `0x132d0`
- `0x13300`
- `0x14240`
- `0x16410`
- `0x19320`
- `0x19460`
- `0x19840`
- `0x198e0`
- `0x1ab60`
- `0x24840`

## callees

- `0x28080`

## string_xrefs

- `0x282f5`: `Common_PageCannotBeNull`

## pseudocode

```c

```

## disassembly

```asm
0x282f0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x282f5  ldstr    aCommonPagecann// "Common_PageCannotBeNull"
0x282fa  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x282ff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28304  ret
```
