# System.Web.Resources.AtlasWeb::get_UpdatePanel_UpdateTooLate

- ea: `0x2b530`
- end: `0x2b545`
- name: `System.Web.Resources.AtlasWeb::get_UpdatePanel_UpdateTooLate`
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

- `0x2b535`: `UpdatePanel_UpdateTooLate`

## pseudocode

```c

```

## disassembly

```asm
0x2b530  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x2b535  ldstr    aUpdatepanelUpd_1// "UpdatePanel_UpdateTooLate"
0x2b53a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x2b53f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x2b544  ret
```
