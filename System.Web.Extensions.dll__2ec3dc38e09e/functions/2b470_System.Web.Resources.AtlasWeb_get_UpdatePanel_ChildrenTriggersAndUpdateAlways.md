# System.Web.Resources.AtlasWeb::get_UpdatePanel_ChildrenTriggersAndUpdateAlways

- ea: `0x2b470`
- end: `0x2b485`
- name: `System.Web.Resources.AtlasWeb::get_UpdatePanel_ChildrenTriggersAndUpdateAlways`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x19b00`

## callees

- `0x28080`

## string_xrefs

- `0x2b475`: `UpdatePanel_ChildrenTriggersAndUpdateAlways`

## pseudocode

```c

```

## disassembly

```asm
0x2b470  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b475  ldstr    aUpdatepanelChi_0// "UpdatePanel_ChildrenTriggersAndUpdateAl"...
0x2b47a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b47f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b484  ret
```
