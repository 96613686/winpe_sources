# System.Web.Resources.AtlasWeb::get_UpdatePanel_SetPartialRenderingModeCalledOnce

- ea: `0x2b4b0`
- end: `0x2b4c5`
- name: `System.Web.Resources.AtlasWeb::get_UpdatePanel_SetPartialRenderingModeCalledOnce`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x19c80`

## callees

- `0x28080`

## string_xrefs

- `0x2b4b5`: `UpdatePanel_SetPartialRenderingModeCalledOnce`

## pseudocode

```c

```

## disassembly

```asm
0x2b4b0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b4b5  ldstr    aUpdatepanelSet// "UpdatePanel_SetPartialRenderingModeCall"...
0x2b4ba  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b4bf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b4c4  ret
```
