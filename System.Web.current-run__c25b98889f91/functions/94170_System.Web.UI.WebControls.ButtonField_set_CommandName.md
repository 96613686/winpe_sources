# System.Web.UI.WebControls.ButtonField::set_CommandName

- ea: `0x94170`
- end: `0x941a0`
- name: `System.Web.UI.WebControls.ButtonField::set_CommandName`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x94320`

## callees

- `0x7d230`
- `0x7d270`
- `0x94170`
- `0xa23d0`
- `0xa2740`

## string_xrefs

- `0x94177`: `CommandName`
- `0x9418e`: `CommandName`

## pseudocode

```c

```

## disassembly

```asm
0x94170  ldarg.1
0x94171  ldarg.0
0x94172  call     instance class System.Web.UI.StateBag System.Web.UI.WebControls.DataControlField::get_ViewState()
0x94177  ldstr    aCommandname// "CommandName"
0x9417c  callvirt instance object System.Web.UI.StateBag::get_Item(string key)
0x94181  call     bool [mscorlib]System.Object::Equals(object, object)
0x94186  brtrue.s loc_9419F
0x94188  ldarg.0
0x94189  call     instance class System.Web.UI.StateBag System.Web.UI.WebControls.DataControlField::get_ViewState()
0x9418e  ldstr    aCommandname// "CommandName"
0x94193  ldarg.1
0x94194  callvirt instance void System.Web.UI.StateBag::set_Item(string key, object value)
0x94199  ldarg.0
0x9419a  callvirt instance void System.Web.UI.WebControls.DataControlField::OnFieldChanged()
0x9419f  ret
```
