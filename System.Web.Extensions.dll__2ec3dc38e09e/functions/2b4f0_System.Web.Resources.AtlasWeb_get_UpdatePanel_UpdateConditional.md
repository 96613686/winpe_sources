# System.Web.Resources.AtlasWeb::get_UpdatePanel_UpdateConditional

- ea: `0x2b4f0`
- end: `0x2b505`
- name: `System.Web.Resources.AtlasWeb::get_UpdatePanel_UpdateConditional`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x19cb0`

## callees

- `0x28080`

## string_xrefs

- `0x2b4f5`: `UpdatePanel_UpdateConditional`

## pseudocode

```c

```

## disassembly

```asm
0x2b4f0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b4f5  ldstr    aUpdatepanelUpd// "UpdatePanel_UpdateConditional"
0x2b4fa  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b4ff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b504  ret
```
