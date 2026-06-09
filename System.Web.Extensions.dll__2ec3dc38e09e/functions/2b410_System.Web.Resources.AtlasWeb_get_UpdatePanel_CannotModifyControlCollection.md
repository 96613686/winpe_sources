# System.Web.Resources.AtlasWeb::get_UpdatePanel_CannotModifyControlCollection

- ea: `0x2b410`
- end: `0x2b425`
- name: `System.Web.Resources.AtlasWeb::get_UpdatePanel_CannotModifyControlCollection`
- size: `21`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x3b010`
- `0x3b040`
- `0x3b070`
- `0x3b0c0`
- `0x3b100`

## callees

- `0x28080`

## string_xrefs

- `0x2b415`: `UpdatePanel_CannotModifyControlCollection`

## pseudocode

```c

```

## disassembly

```asm
0x2b410  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b415  ldstr    aUpdatepanelCan// "UpdatePanel_CannotModifyControlCollecti"...
0x2b41a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b41f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b424  ret
```
