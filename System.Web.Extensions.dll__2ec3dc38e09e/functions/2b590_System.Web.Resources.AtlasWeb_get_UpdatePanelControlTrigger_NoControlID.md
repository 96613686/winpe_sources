# System.Web.Resources.AtlasWeb::get_UpdatePanelControlTrigger_NoControlID

- ea: `0x2b590`
- end: `0x2b5a5`
- name: `System.Web.Resources.AtlasWeb::get_UpdatePanelControlTrigger_NoControlID`
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

- `0x2b595`: `UpdatePanelControlTrigger_NoControlID`

## pseudocode

```c

```

## disassembly

```asm
0x2b590  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b595  ldstr    aUpdatepanelcon_1// "UpdatePanelControlTrigger_NoControlID"
0x2b59a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b59f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b5a4  ret
```
