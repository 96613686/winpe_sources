# System.Web.UI.WebControls.CreateUserWizard::get_ConfirmPasswordCompareErrorMessage

- ea: `0x9db50`
- end: `0x9db76`
- name: `System.Web.UI.WebControls.CreateUserWizard::get_ConfirmPasswordCompareErrorMessage`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x9f000`
- `0x19dee0`

## callees

- `0x34fa0`
- `0x61290`
- `0x7d230`
- `0x9db50`

## string_xrefs

- `0x9db56`: `ConfirmPasswordCompareErrorMessage`
- `0x9db6b`: `CreateUserWizard_DefaultConfirmPasswordCompareErrorMessage`

## pseudocode

```c

```

## disassembly

```asm
0x9db50  ldarg.0
0x9db51  callvirt instance class System.Web.UI.StateBag System.Web.UI.Control::get_ViewState()
0x9db56  ldstr    aConfirmpasswor// "ConfirmPasswordCompareErrorMessage"
0x9db5b  callvirt instance object System.Web.UI.StateBag::get_Item(string key)
0x9db60  stloc.0
0x9db61  ldloc.0
0x9db62  brfalse.s loc_9DB6B
0x9db64  ldloc.0
0x9db65  castclass [mscorlib]System.String
0x9db6a  ret
0x9db6b  ldstr    aCreateuserwiza_4// "CreateUserWizard_DefaultConfirmPassword"...
0x9db70  call     string System.Web.SR::GetString(string name)
0x9db75  ret
```
