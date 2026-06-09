# System.Web.UI.WebControls.CommandField::get_DeleteText

- ea: `0x9bc60`
- end: `0x9bc86`
- name: `System.Web.UI.WebControls.CommandField::get_DeleteText`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x9c330`
- `0x9c490`

## callees

- `0x34fa0`
- `0x7d230`
- `0x9bc60`
- `0xa23d0`

## string_xrefs

- `0x9bc66`: `DeleteText`
- `0x9bc7b`: `CommandField_DefaultDeleteCaption`

## pseudocode

```c

```

## disassembly

```asm
0x9bc60  ldarg.0
0x9bc61  call     instance class System.Web.UI.StateBag System.Web.UI.WebControls.DataControlField::get_ViewState()
0x9bc66  ldstr    aDeletetext// "DeleteText"
0x9bc6b  callvirt instance object System.Web.UI.StateBag::get_Item(string key)
0x9bc70  stloc.0
0x9bc71  ldloc.0
0x9bc72  brfalse.s loc_9BC7B
0x9bc74  ldloc.0
0x9bc75  castclass [mscorlib]System.String
0x9bc7a  ret
0x9bc7b  ldstr    aCommandfieldDe_0// "CommandField_DefaultDeleteCaption"
0x9bc80  call     string System.Web.SR::GetString(string name)
0x9bc85  ret
```
