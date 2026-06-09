# System.Web.UI.WebControls.CommandField::set_UpdateText

- ea: `0x9c230`
- end: `0x9c260`
- name: `System.Web.UI.WebControls.CommandField::set_UpdateText`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9c330`

## callees

- `0x7d230`
- `0x7d270`
- `0x9c230`
- `0xa23d0`
- `0xa2740`

## string_xrefs

- `0x9c237`: `UpdateText`
- `0x9c24e`: `UpdateText`

## pseudocode

```c

```

## disassembly

```asm
0x9c230  ldarg.1
0x9c231  ldarg.0
0x9c232  call     instance class System.Web.UI.StateBag System.Web.UI.WebControls.DataControlField::get_ViewState()
0x9c237  ldstr    aUpdatetext// "UpdateText"
0x9c23c  callvirt instance object System.Web.UI.StateBag::get_Item(string key)
0x9c241  call     bool [mscorlib]System.Object::Equals(object, object)
0x9c246  brtrue.s loc_9C25F
0x9c248  ldarg.0
0x9c249  call     instance class System.Web.UI.StateBag System.Web.UI.WebControls.DataControlField::get_ViewState()
0x9c24e  ldstr    aUpdatetext// "UpdateText"
0x9c253  ldarg.1
0x9c254  callvirt instance void System.Web.UI.StateBag::set_Item(string key, object value)
0x9c259  ldarg.0
0x9c25a  callvirt instance void System.Web.UI.WebControls.DataControlField::OnFieldChanged()
0x9c25f  ret
```
