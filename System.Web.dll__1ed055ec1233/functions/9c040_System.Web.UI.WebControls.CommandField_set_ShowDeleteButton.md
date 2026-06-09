# System.Web.UI.WebControls.CommandField::set_ShowDeleteButton

- ea: `0x9c040`
- end: `0x9c07a`
- name: `System.Web.UI.WebControls.CommandField::set_ShowDeleteButton`
- size: `58`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x9c330`
- `0xa91b0`
- `0xb4ae0`

## callees

- `0x7d230`
- `0x7d270`
- `0x9c040`
- `0xa23d0`
- `0xa2740`

## string_xrefs

- `0x9c046`: `ShowDeleteButton`
- `0x9c063`: `ShowDeleteButton`

## pseudocode

```c

```

## disassembly

```asm
0x9c040  ldarg.0
0x9c041  call     instance class System.Web.UI.StateBag System.Web.UI.WebControls.DataControlField::get_ViewState()
0x9c046  ldstr    aShowdeletebutt// "ShowDeleteButton"
0x9c04b  callvirt instance object System.Web.UI.StateBag::get_Item(string key)
0x9c050  stloc.0
0x9c051  ldloc.0
0x9c052  brfalse.s loc_9C05D
0x9c054  ldloc.0
0x9c055  unbox.any [mscorlib]System.Boolean
0x9c05a  ldarg.1
0x9c05b  beq.s    loc_9C079
0x9c05d  ldarg.0
0x9c05e  call     instance class System.Web.UI.StateBag System.Web.UI.WebControls.DataControlField::get_ViewState()
0x9c063  ldstr    aShowdeletebutt// "ShowDeleteButton"
0x9c068  ldarg.1
0x9c069  box      [mscorlib]System.Boolean
0x9c06e  callvirt instance void System.Web.UI.StateBag::set_Item(string key, object value)
0x9c073  ldarg.0
0x9c074  callvirt instance void System.Web.UI.WebControls.DataControlField::OnFieldChanged()
0x9c079  ret
```
