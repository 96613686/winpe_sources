# System.Web.Resources.AtlasWeb::get_ListView_InvalidCommand

- ea: `0x29b30`
- end: `0x29b45`
- name: `System.Web.Resources.AtlasWeb::get_ListView_InvalidCommand`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x20920`

## callees

- `0x28080`

## string_xrefs

- `0x29b35`: `ListView_InvalidCommand`

## pseudocode

```c

```

## disassembly

```asm
0x29b30  call     class [mscorlib]System.Resources.ResourceManager System.Web.Resources.AtlasWeb::get_ResourceManager()
0x29b35  ldstr    aListviewInvali_0// "ListView_InvalidCommand"
0x29b3a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Web.Resources.AtlasWeb::resourceCulture
0x29b3f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x29b44  ret
```
