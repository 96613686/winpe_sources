# ConvertToTemplateHelper::.cctor_0

- ea: `0xf90c0`
- end: `0xf9143`
- name: `ConvertToTemplateHelper::.cctor_0`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0xf9124`: `HelpLink`
- `0xf9112`: `CreateUserLink`
- `0xf911b`: `PasswordRecoveryLink`
- `0xf9101`: `LoginLinkButton`

## pseudocode

```c

```

## disassembly

```asm
0xf90c0  ldc.i4.s 0xC
0xf90c2  newarr   [mscorlib]System.String
0xf90c7  dup
0xf90c8  ldc.i4.0
0xf90c9  ldstr    aUsername// "UserName"
0xf90ce  stelem.ref
0xf90cf  dup
0xf90d0  ldc.i4.1
0xf90d1  ldstr    aUsernamerequir_0// "UserNameRequired"
0xf90d6  stelem.ref
0xf90d7  dup
0xf90d8  ldc.i4.2
0xf90d9  ldstr    aPassword// "Password"
0xf90de  stelem.ref
0xf90df  dup
0xf90e0  ldc.i4.3
0xf90e1  ldstr    aPasswordrequir_0// "PasswordRequired"
0xf90e6  stelem.ref
0xf90e7  dup
0xf90e8  ldc.i4.4
0xf90e9  ldstr    aRememberme// "RememberMe"
0xf90ee  stelem.ref
0xf90ef  dup
0xf90f0  ldc.i4.5
0xf90f1  ldstr    aLoginbutton// "LoginButton"
0xf90f6  stelem.ref
0xf90f7  dup
0xf90f8  ldc.i4.6
0xf90f9  ldstr    aLoginimagebutt// "LoginImageButton"
0xf90fe  stelem.ref
0xf90ff  dup
0xf9100  ldc.i4.7
0xf9101  ldstr    aLoginlinkbutto// "LoginLinkButton"
0xf9106  stelem.ref
0xf9107  dup
0xf9108  ldc.i4.8
0xf9109  ldstr    aFailuretext// "FailureText"
0xf910e  stelem.ref
0xf910f  dup
0xf9110  ldc.i4.s 9
0xf9112  ldstr    aCreateuserlink// "CreateUserLink"
0xf9117  stelem.ref
0xf9118  dup
0xf9119  ldc.i4.s 0xA
0xf911b  ldstr    aPasswordrecove_8// "PasswordRecoveryLink"
0xf9120  stelem.ref
0xf9121  dup
0xf9122  ldc.i4.s 0xB
0xf9124  ldstr    aHelplink// "HelpLink"
0xf9129  stelem.ref
0xf912a  stsfld   string[] ConvertToTemplateHelper::_persistedControlIDs
0xf912f  ldc.i4.1
0xf9130  newarr   [mscorlib]System.String
0xf9135  dup
0xf9136  ldc.i4.0
0xf9137  ldstr    aFailuretext// "FailureText"
0xf913c  stelem.ref
0xf913d  stsfld   string[] ConvertToTemplateHelper::_persistedIfNotVisibleControlIDs
0xf9142  ret
```
