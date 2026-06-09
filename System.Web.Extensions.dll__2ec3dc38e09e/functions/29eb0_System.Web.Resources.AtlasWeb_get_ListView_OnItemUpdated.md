# System.Web.Resources.AtlasWeb::get_ListView_OnItemUpdated

- ea: `0x29eb0`
- end: `0x29ec5`
- name: `System.Web.Resources.AtlasWeb::get_ListView_OnItemUpdated`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x28080`

## string_xrefs

- `0x29eb5`: `ListView_OnItemUpdated`

## pseudocode

```c

```

## disassembly

```asm
0x29eb0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x29eb5  ldstr    aListviewOnitem_8// "ListView_OnItemUpdated"
0x29eba  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x29ebf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x29ec4  ret
```
