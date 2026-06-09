# System.Web.UI.WebControls.CommandField::set_UpdateImageUrl

- ea: `0x9c1d0`
- end: `0x9c200`
- name: `System.Web.UI.WebControls.CommandField::set_UpdateImageUrl`
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
- `0x9c1d0`
- `0xa23d0`
- `0xa2740`

## string_xrefs

- `0x9c1d7`: `UpdateImageUrl`
- `0x9c1ee`: `UpdateImageUrl`

## pseudocode

```c

```

## disassembly

```asm
0x9c1d0  ldarg.1
0x9c1d1  ldarg.0
0x9c1d2  call     instance class System.Web.UI.StateBag System.Web.UI.WebControls.DataControlField::get_ViewState()
0x9c1d7  ldstr    aUpdateimageurl// "UpdateImageUrl"
0x9c1dc  callvirt instance object System.Web.UI.StateBag::get_Item(string key)
0x9c1e1  call     bool [mscorlib]System.Object::Equals(object, object)
0x9c1e6  brtrue.s loc_9C1FF
0x9c1e8  ldarg.0
0x9c1e9  call     instance class System.Web.UI.StateBag System.Web.UI.WebControls.DataControlField::get_ViewState()
0x9c1ee  ldstr    aUpdateimageurl// "UpdateImageUrl"
0x9c1f3  ldarg.1
0x9c1f4  callvirt instance void System.Web.UI.StateBag::set_Item(string key, object value)
0x9c1f9  ldarg.0
0x9c1fa  callvirt instance void System.Web.UI.WebControls.DataControlField::OnFieldChanged()
0x9c1ff  ret
```
