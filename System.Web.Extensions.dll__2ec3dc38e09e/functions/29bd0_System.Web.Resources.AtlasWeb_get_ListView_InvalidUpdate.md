# System.Web.Resources.AtlasWeb::get_ListView_InvalidUpdate

- ea: `0x29bd0`
- end: `0x29be5`
- name: `System.Web.Resources.AtlasWeb::get_ListView_InvalidUpdate`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x20cb0`

## callees

- `0x28080`

## string_xrefs

- `0x29bd5`: `ListView_InvalidUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x29bd0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x29bd5  ldstr    aListviewInvali_5// "ListView_InvalidUpdate"
0x29bda  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x29bdf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x29be4  ret
```
