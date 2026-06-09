# System.Web.Resources.AtlasWeb::get_ScriptManager_UpdatePanelNotRegistered

- ea: `0x2af50`
- end: `0x2af65`
- name: `System.Web.Resources.AtlasWeb::get_ScriptManager_UpdatePanelNotRegistered`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x11c70`

## callees

- `0x28080`

## string_xrefs

- `0x2af55`: `ScriptManager_UpdatePanelNotRegistered`

## pseudocode

```c

```

## disassembly

```asm
0x2af50  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2af55  ldstr    aScriptmanagerU// "ScriptManager_UpdatePanelNotRegistered"
0x2af5a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2af5f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2af64  ret
```
