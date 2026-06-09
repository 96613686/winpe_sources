# System.Web.Resources.AtlasWeb::get_UpdatePanelControlTrigger_ControlNotFound

- ea: `0x2b570`
- end: `0x2b585`
- name: `System.Web.Resources.AtlasWeb::get_UpdatePanelControlTrigger_ControlNotFound`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x19d80`

## callees

- `0x28080`

## string_xrefs

- `0x2b575`: `UpdatePanelControlTrigger_ControlNotFound`

## pseudocode

```c

```

## disassembly

```asm
0x2b570  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b575  ldstr    aUpdatepanelcon_0// "UpdatePanelControlTrigger_ControlNotFou"...
0x2b57a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b57f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b584  ret
```
