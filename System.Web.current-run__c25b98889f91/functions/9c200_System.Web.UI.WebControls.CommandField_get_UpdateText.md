# System.Web.UI.WebControls.CommandField::get_UpdateText

- ea: `0x9c200`
- end: `0x9c226`
- name: `System.Web.UI.WebControls.CommandField::get_UpdateText`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9c330`
- `0x9c490`

## callees

- `0x34fa0`
- `0x7d230`
- `0x9c200`
- `0xa23d0`

## string_xrefs

- `0x9c206`: `UpdateText`
- `0x9c21b`: `CommandField_DefaultUpdateCaption`

## pseudocode

```c

```

## disassembly

```asm
0x9c200  ldarg.0
0x9c201  call     instance class System.Web.UI.StateBag System.Web.UI.WebControls.DataControlField::get_ViewState()
0x9c206  ldstr    aUpdatetext// "UpdateText"
0x9c20b  callvirt instance object System.Web.UI.StateBag::get_Item(string key)
0x9c210  stloc.0
0x9c211  ldloc.0
0x9c212  brfalse.s loc_9C21B
0x9c214  ldloc.0
0x9c215  castclass [mscorlib]System.String
0x9c21a  ret
0x9c21b  ldstr    aCommandfieldDe_5// "CommandField_DefaultUpdateCaption"
0x9c220  call     string System.Web.SR::GetString(string name)
0x9c225  ret
```
