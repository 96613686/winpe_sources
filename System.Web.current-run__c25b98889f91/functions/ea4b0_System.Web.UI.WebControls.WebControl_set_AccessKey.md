# System.Web.UI.WebControls.WebControl::set_AccessKey

- ea: `0xea4b0`
- end: `0xea4ef`
- name: `System.Web.UI.WebControls.WebControl::set_AccessKey`
- size: `63`
- prototype: ``
- caller_count: `19`
- callee_count: `5`
- tags: ``

## callers

- `0x84bd0`
- `0x8ebb0`
- `0x8f460`
- `0x98b00`
- `0x993b0`
- `0x9aa80`
- `0x9adc0`
- `0x9f000`
- `0x9f830`
- `0xc0bd0`
- `0xc3c50`
- `0xd2df0`
- `0xd3350`
- `0xe52b0`
- `0xeabe0`
- `0xf7310`
- `0xf7b70`
- `0xfa7a0`
- `0x110800`

## callees

- `0x34fa0`
- `0x58a50`
- `0x61290`
- `0x7d270`
- `0xea4b0`

## string_xrefs

- `0xea4d7`: `AccessKey`
- `0xea4c1`: `WebControl_InvalidAccessKey`

## pseudocode

```c

```

## disassembly

```asm
0xea4b0  ldarg.1
0xea4b1  brfalse.s loc_EA4D1
0xea4b3  ldarg.1
0xea4b4  callvirt instance int32 [mscorlib]System.String::get_Length()
0xea4b9  ldc.i4.1
0xea4ba  ble.s    loc_EA4D1
0xea4bc  ldstr    aValue// "value"
0xea4c1  ldstr    aWebcontrolInva// "WebControl_InvalidAccessKey"
0xea4c6  call     string System.Web.SR::GetString(string name)
0xea4cb  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0xea4d0  throw
0xea4d1  ldarg.0
0xea4d2  callvirt instance class System.Web.UI.StateBag System.Web.UI.Control::get_ViewState()
0xea4d7  ldstr    aAccesskey_1// "AccessKey"
0xea4dc  ldarg.1
0xea4dd  callvirt instance void System.Web.UI.StateBag::set_Item(string key, object value)
0xea4e2  ldarg.0
0xea4e3  ldflda   valuetype System.Web.Util.SimpleBitVector32 System.Web.UI.WebControls.WebControl::_webControlFlags
0xea4e8  ldc.i4.4
0xea4e9  call     instance void System.Web.Util.SimpleBitVector32::Set(int32 bit)
0xea4ee  ret
```
