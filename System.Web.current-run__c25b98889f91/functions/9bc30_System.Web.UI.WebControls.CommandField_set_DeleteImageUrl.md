# System.Web.UI.WebControls.CommandField::set_DeleteImageUrl

- ea: `0x9bc30`
- end: `0x9bc60`
- name: `System.Web.UI.WebControls.CommandField::set_DeleteImageUrl`
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
- `0x9bc30`
- `0xa23d0`
- `0xa2740`

## string_xrefs

- `0x9bc37`: `DeleteImageUrl`
- `0x9bc4e`: `DeleteImageUrl`

## pseudocode

```c

```

## disassembly

```asm
0x9bc30  ldarg.1
0x9bc31  ldarg.0
0x9bc32  call     instance class System.Web.UI.StateBag System.Web.UI.WebControls.DataControlField::get_ViewState()
0x9bc37  ldstr    aDeleteimageurl// "DeleteImageUrl"
0x9bc3c  callvirt instance object System.Web.UI.StateBag::get_Item(string key)
0x9bc41  call     bool [mscorlib]System.Object::Equals(object, object)
0x9bc46  brtrue.s loc_9BC5F
0x9bc48  ldarg.0
0x9bc49  call     instance class System.Web.UI.StateBag System.Web.UI.WebControls.DataControlField::get_ViewState()
0x9bc4e  ldstr    aDeleteimageurl// "DeleteImageUrl"
0x9bc53  ldarg.1
0x9bc54  callvirt instance void System.Web.UI.StateBag::set_Item(string key, object value)
0x9bc59  ldarg.0
0x9bc5a  callvirt instance void System.Web.UI.WebControls.DataControlField::OnFieldChanged()
0x9bc5f  ret
```
