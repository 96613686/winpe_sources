# System.Web.UI.WebControls.ListView::get_ItemPlaceholderID

- ea: `0x1e9f0`
- end: `0x1ea11`
- name: `System.Web.UI.WebControls.ListView::get_ItemPlaceholderID`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x203d0`

## callees

- `0x1e9f0`

## string_xrefs

- `0x1e9f6`: `ItemPlaceholderID`
- `0x1ea0b`: `itemPlaceholder`

## pseudocode

```c

```

## disassembly

```asm
0x1e9f0  ldarg.0
0x1e9f1  callvirt instance class [System.Web]System.Web.UI.StateBag [System.Web]System.Web.UI.Control::get_ViewState()
0x1e9f6  ldstr    aItemplaceholde// "ItemPlaceholderID"
0x1e9fb  callvirt instance object [System.Web]System.Web.UI.StateBag::get_Item(string)
0x1ea00  stloc.0
0x1ea01  ldloc.0
0x1ea02  brfalse.s loc_1EA0B
0x1ea04  ldloc.0
0x1ea05  castclass [mscorlib]System.String
0x1ea0a  ret
0x1ea0b  ldstr    aItemplaceholde_0// "itemPlaceholder"
0x1ea10  ret
```
