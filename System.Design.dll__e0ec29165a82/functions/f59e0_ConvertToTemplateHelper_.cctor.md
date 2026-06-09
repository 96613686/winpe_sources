# ConvertToTemplateHelper::.cctor

- ea: `0xf59e0`
- end: `0xf5ad8`
- name: `ConvertToTemplateHelper::.cctor`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## string_xrefs

- `0xf5a95`: `HelpLink`
- `0xf5ab0`: `EditProfileLink`
- `0xf5a32`: `NewPasswordCompare`
- `0xf5a4d`: `ChangePasswordLinkButton`
- `0xf5a68`: `CancelLinkButton`
- `0xf5a83`: `ContinueLinkButton`
- `0xf5a9e`: `CreateUserLink`
- `0xf5aa7`: `PasswordRecoveryLink`
- `0xf5ab9`: `EditProfileLinkSuccess`

## pseudocode

```c

```

## disassembly

```asm
0xf59e0  ldc.i4.s 0x19
0xf59e2  newarr   [mscorlib]System.String
0xf59e7  dup
0xf59e8  ldc.i4.0
0xf59e9  ldstr    aUsername// "UserName"
0xf59ee  stelem.ref
0xf59ef  dup
0xf59f0  ldc.i4.1
0xf59f1  ldstr    aUsernamerequir_0// "UserNameRequired"
0xf59f6  stelem.ref
0xf59f7  dup
0xf59f8  ldc.i4.2
0xf59f9  ldstr    aCurrentpasswor// "CurrentPassword"
0xf59fe  stelem.ref
0xf59ff  dup
0xf5a00  ldc.i4.3
0xf5a01  ldstr    aCurrentpasswor_0// "CurrentPasswordRequired"
0xf5a06  stelem.ref
0xf5a07  dup
0xf5a08  ldc.i4.4
0xf5a09  ldstr    aNewpassword// "NewPassword"
0xf5a0e  stelem.ref
0xf5a0f  dup
0xf5a10  ldc.i4.5
0xf5a11  ldstr    aNewpasswordreq_0// "NewPasswordRequired"
0xf5a16  stelem.ref
0xf5a17  dup
0xf5a18  ldc.i4.6
0xf5a19  ldstr    aNewpasswordreg_1// "NewPasswordRegExp"
0xf5a1e  stelem.ref
0xf5a1f  dup
0xf5a20  ldc.i4.7
0xf5a21  ldstr    aConfirmnewpass_0// "ConfirmNewPassword"
0xf5a26  stelem.ref
0xf5a27  dup
0xf5a28  ldc.i4.8
0xf5a29  ldstr    aConfirmnewpass_1// "ConfirmNewPasswordRequired"
0xf5a2e  stelem.ref
0xf5a2f  dup
0xf5a30  ldc.i4.s 9
0xf5a32  ldstr    aNewpasswordcom// "NewPasswordCompare"
0xf5a37  stelem.ref
0xf5a38  dup
0xf5a39  ldc.i4.s 0xA
0xf5a3b  ldstr    aChangepassword_13// "ChangePasswordPushButton"
0xf5a40  stelem.ref
0xf5a41  dup
0xf5a42  ldc.i4.s 0xB
0xf5a44  ldstr    aChangepassword_14// "ChangePasswordImageButton"
0xf5a49  stelem.ref
0xf5a4a  dup
0xf5a4b  ldc.i4.s 0xC
0xf5a4d  ldstr    aChangepassword_15// "ChangePasswordLinkButton"
0xf5a52  stelem.ref
0xf5a53  dup
0xf5a54  ldc.i4.s 0xD
0xf5a56  ldstr    aCancelpushbutt// "CancelPushButton"
0xf5a5b  stelem.ref
0xf5a5c  dup
0xf5a5d  ldc.i4.s 0xE
0xf5a5f  ldstr    aCancelimagebut// "CancelImageButton"
0xf5a64  stelem.ref
0xf5a65  dup
0xf5a66  ldc.i4.s 0xF
0xf5a68  ldstr    aCancellinkbutt// "CancelLinkButton"
0xf5a6d  stelem.ref
0xf5a6e  dup
0xf5a6f  ldc.i4.s 0x10
0xf5a71  ldstr    aContinuepushbu// "ContinuePushButton"
0xf5a76  stelem.ref
0xf5a77  dup
0xf5a78  ldc.i4.s 0x11
0xf5a7a  ldstr    aContinueimageb// "ContinueImageButton"
0xf5a7f  stelem.ref
0xf5a80  dup
0xf5a81  ldc.i4.s 0x12
0xf5a83  ldstr    aContinuelinkbu// "ContinueLinkButton"
0xf5a88  stelem.ref
0xf5a89  dup
0xf5a8a  ldc.i4.s 0x13
0xf5a8c  ldstr    aFailuretext// "FailureText"
0xf5a91  stelem.ref
0xf5a92  dup
0xf5a93  ldc.i4.s 0x14
0xf5a95  ldstr    aHelplink// "HelpLink"
0xf5a9a  stelem.ref
0xf5a9b  dup
0xf5a9c  ldc.i4.s 0x15
0xf5a9e  ldstr    aCreateuserlink// "CreateUserLink"
0xf5aa3  stelem.ref
0xf5aa4  dup
0xf5aa5  ldc.i4.s 0x16
0xf5aa7  ldstr    aPasswordrecove_8// "PasswordRecoveryLink"
0xf5aac  stelem.ref
0xf5aad  dup
0xf5aae  ldc.i4.s 0x17
0xf5ab0  ldstr    aEditprofilelin// "EditProfileLink"
0xf5ab5  stelem.ref
0xf5ab6  dup
0xf5ab7  ldc.i4.s 0x18
0xf5ab9  ldstr    aEditprofilelin_0// "EditProfileLinkSuccess"
0xf5abe  stelem.ref
0xf5abf  stsfld   string[] ConvertToTemplateHelper::_persistedControlIDs
0xf5ac4  ldc.i4.1
0xf5ac5  newarr   [mscorlib]System.String
0xf5aca  dup
0xf5acb  ldc.i4.0
0xf5acc  ldstr    aFailuretext// "FailureText"
0xf5ad1  stelem.ref
0xf5ad2  stsfld   string[] ConvertToTemplateHelper::_persistedIfNotVisibleControlIDs
0xf5ad7  ret
```
