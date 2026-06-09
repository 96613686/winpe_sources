# System.Web.Resources.AtlasWeb::get_Common_NullOrEmpty

- ea: `0x282d0`
- end: `0x282e5`
- name: `System.Web.Resources.AtlasWeb::get_Common_NullOrEmpty`
- size: `21`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x12cb0`
- `0x12ce0`
- `0x12de0`
- `0x12e00`
- `0x12e30`
- `0x12e60`
- `0x12eb0`
- `0x12ee0`
- `0x18160`
- `0x18ac0`
- `0x18bd0`
- `0x18c60`

## callees

- `0x28080`

## string_xrefs

- `0x282d5`: `Common_NullOrEmpty`

## pseudocode

```c

```

## disassembly

```asm
0x282d0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x282d5  ldstr    aCommonNullorem// "Common_NullOrEmpty"
0x282da  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x282df  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x282e4  ret
```
