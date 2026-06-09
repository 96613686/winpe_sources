# System.Web.UI.WebControls.ChangePassword::get_ConfirmPasswordCompareErrorMessage

- ea: `0x96fe0`
- end: `0x97006`
- name: `System.Web.UI.WebControls.ChangePassword::get_ConfirmPasswordCompareErrorMessage`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x98b00`
- `0x19cba0`

## callees

- `0x34fa0`
- `0x61290`
- `0x7d230`
- `0x96fe0`

## string_xrefs

- `0x96fe6`: `ConfirmPasswordCompareErrorMessage`
- `0x96ffb`: `ChangePassword_DefaultConfirmPasswordCompareErrorMessage`

## pseudocode

```c

```

## disassembly

```asm
0x96fe0  ldarg.0
0x96fe1  callvirt instance class System.Web.UI.StateBag System.Web.UI.Control::get_ViewState()
0x96fe6  ldstr    aConfirmpasswor// "ConfirmPasswordCompareErrorMessage"
0x96feb  callvirt instance object System.Web.UI.StateBag::get_Item(string key)
0x96ff0  stloc.0
0x96ff1  ldloc.0
0x96ff2  brfalse.s loc_96FFB
0x96ff4  ldloc.0
0x96ff5  castclass [mscorlib]System.String
0x96ffa  ret
0x96ffb  ldstr    aChangepassword_10// "ChangePassword_DefaultConfirmPasswordCo"...
0x97000  call     string System.Web.SR::GetString(string name)
0x97005  ret
```
