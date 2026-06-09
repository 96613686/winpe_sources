# System.Web.Resources.AtlasWeb::get_ListView_OnItemCommand

- ea: `0x29db0`
- end: `0x29dc5`
- name: `System.Web.Resources.AtlasWeb::get_ListView_OnItemCommand`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x28080`

## string_xrefs

- `0x29db5`: `ListView_OnItemCommand`

## pseudocode

```c

```

## disassembly

```asm
0x29db0  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x29db5  ldstr    aListviewOnitem_0// "ListView_OnItemCommand"
0x29dba  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x29dbf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x29dc4  ret
```
