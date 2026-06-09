# System.Web.UI.WebControls.CommandField::set_DeleteText

- ea: `0x9bc90`
- end: `0x9bcc0`
- name: `System.Web.UI.WebControls.CommandField::set_DeleteText`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x9c330`

## callees

- `0x7d230`
- `0x7d270`
- `0x9bc90`
- `0xa23d0`
- `0xa2740`

## string_xrefs

- `0x9bc97`: `DeleteText`
- `0x9bcae`: `DeleteText`

## pseudocode

```c

```

## disassembly

```asm
0x9bc90  ldarg.1
0x9bc91  ldarg.0
0x9bc92  call     instance class System.Web.UI.StateBag System.Web.UI.WebControls.DataControlField::get_ViewState()
0x9bc97  ldstr    aDeletetext// "DeleteText"
0x9bc9c  callvirt instance object System.Web.UI.StateBag::get_Item(string key)
0x9bca1  call     bool [mscorlib]System.Object::Equals(object, object)
0x9bca6  brtrue.s loc_9BCBF
0x9bca8  ldarg.0
0x9bca9  call     instance class System.Web.UI.StateBag System.Web.UI.WebControls.DataControlField::get_ViewState()
0x9bcae  ldstr    aDeletetext// "DeleteText"
0x9bcb3  ldarg.1
0x9bcb4  callvirt instance void System.Web.UI.StateBag::set_Item(string key, object value)
0x9bcb9  ldarg.0
0x9bcba  callvirt instance void System.Web.UI.WebControls.DataControlField::OnFieldChanged()
0x9bcbf  ret
```
