# System.Web.Resources.AtlasWeb::get_Common_ScriptManagerRequired

- ea: `0x28310`
- end: `0x28325`
- name: `System.Web.Resources.AtlasWeb::get_Common_ScriptManagerRequired`
- size: `21`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xf540`
- `0x10360`
- `0x11fc0`
- `0x13300`
- `0x16410`
- `0x19460`
- `0x198e0`
- `0x1a0f0`

## callees

- `0x28080`

## string_xrefs

- `0x28315`: `Common_ScriptManagerRequired`

## pseudocode

```c

```

## disassembly

```asm
0x28310  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x28315  ldstr    aCommonScriptma// "Common_ScriptManagerRequired"
0x2831a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2831f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x28324  ret
```
