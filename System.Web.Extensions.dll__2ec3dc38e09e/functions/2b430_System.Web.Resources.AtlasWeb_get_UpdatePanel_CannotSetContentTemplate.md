# System.Web.Resources.AtlasWeb::get_UpdatePanel_CannotSetContentTemplate

- ea: `0x2b430`
- end: `0x2b445`
- name: `System.Web.Resources.AtlasWeb::get_UpdatePanel_CannotSetContentTemplate`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x197a0`

## callees

- `0x28080`

## string_xrefs

- `0x2b435`: `UpdatePanel_CannotSetContentTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x2b430  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b435  ldstr    aUpdatepanelCan_0// "UpdatePanel_CannotSetContentTemplate"
0x2b43a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b43f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b444  ret
```
