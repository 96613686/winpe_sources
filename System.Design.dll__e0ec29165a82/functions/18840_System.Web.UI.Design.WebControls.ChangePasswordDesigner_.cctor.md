# System.Web.UI.Design.WebControls.ChangePasswordDesigner::.cctor

- ea: `0x18840`
- end: `0x18a88`
- name: `System.Web.UI.Design.WebControls.ChangePasswordDesigner::.cctor`
- size: `584`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x18848`: `ChangePasswordTemplate`
- `0x18850`: `SuccessTemplate`
- `0x1891d`: `ConfirmPasswordCompareErrorMessage`
- `0x18953`: `CreateUserIconUrl`
- `0x1895c`: `CreateUserText`
- `0x18965`: `CreateUserUrl`
- `0x189b6`: `HyperLinkStyle`

## pseudocode

```c

```

## disassembly

```asm
0x18840  ldc.i4.2
0x18841  newarr   [mscorlib]System.String
0x18846  dup
0x18847  ldc.i4.0
0x18848  ldstr    aChangepassword_5// "ChangePasswordTemplate"
0x1884d  stelem.ref
0x1884e  dup
0x1884f  ldc.i4.1
0x18850  ldstr    aSuccesstemplat// "SuccessTemplate"
0x18855  stelem.ref
0x18856  stsfld   string[] System.Web.UI.Design.WebControls.ChangePasswordDesigner::_templateNames
0x1885b  ldc.i4.7
0x1885c  newarr   [mscorlib]System.String
0x18861  dup
0x18862  ldc.i4.0
0x18863  ldstr    aChangepassword_6// "ChangePasswordTitleText"
0x18868  stelem.ref
0x18869  dup
0x1886a  ldc.i4.1
0x1886b  ldstr    aUsernamelabelt// "UserNameLabelText"
0x18870  stelem.ref
0x18871  dup
0x18872  ldc.i4.2
0x18873  ldstr    aPasswordlabelt// "PasswordLabelText"
0x18878  stelem.ref
0x18879  dup
0x1887a  ldc.i4.3
0x1887b  ldstr    aInstructiontex_1// "InstructionText"
0x18880  stelem.ref
0x18881  dup
0x18882  ldc.i4.4
0x18883  ldstr    aPasswordhintte// "PasswordHintText"
0x18888  stelem.ref
0x18889  dup
0x1888a  ldc.i4.5
0x1888b  ldstr    aNewpasswordlab// "NewPasswordLabelText"
0x18890  stelem.ref
0x18891  dup
0x18892  ldc.i4.6
0x18893  ldstr    aConfirmnewpass// "ConfirmNewPasswordLabelText"
0x18898  stelem.ref
0x18899  stsfld   string[] System.Web.UI.Design.WebControls.ChangePasswordDesigner::_changePasswordViewRegionToPropertyMap
0x1889e  ldc.i4.2
0x1889f  newarr   [mscorlib]System.String
0x188a4  dup
0x188a5  ldc.i4.0
0x188a6  ldstr    aSuccesstext// "SuccessText"
0x188ab  stelem.ref
0x188ac  dup
0x188ad  ldc.i4.1
0x188ae  ldstr    aSuccesstitlete// "SuccessTitleText"
0x188b3  stelem.ref
0x188b4  stsfld   string[] System.Web.UI.Design.WebControls.ChangePasswordDesigner::_successViewRegionToPropertyMap
0x188b9  ldc.i4.s 0x33
0x188bb  newarr   [mscorlib]System.String
0x188c0  dup
0x188c1  ldc.i4.0
0x188c2  ldstr    aBorderpadding// "BorderPadding"
0x188c7  stelem.ref
0x188c8  dup
0x188c9  ldc.i4.1
0x188ca  ldstr    aCancelbuttonim// "CancelButtonImageUrl"
0x188cf  stelem.ref
0x188d0  dup
0x188d1  ldc.i4.2
0x188d2  ldstr    aCancelbuttonst// "CancelButtonStyle"
0x188d7  stelem.ref
0x188d8  dup
0x188d9  ldc.i4.3
0x188da  ldstr    aCancelbuttonte// "CancelButtonText"
0x188df  stelem.ref
0x188e0  dup
0x188e1  ldc.i4.4
0x188e2  ldstr    aCancelbuttonty// "CancelButtonType"
0x188e7  stelem.ref
0x188e8  dup
0x188e9  ldc.i4.5
0x188ea  ldstr    aChangepassword_7// "ChangePasswordButtonImageUrl"
0x188ef  stelem.ref
0x188f0  dup
0x188f1  ldc.i4.6
0x188f2  ldstr    aChangepassword_8// "ChangePasswordButtonStyle"
0x188f7  stelem.ref
0x188f8  dup
0x188f9  ldc.i4.7
0x188fa  ldstr    aChangepassword_9// "ChangePasswordButtonText"
0x188ff  stelem.ref
0x18900  dup
0x18901  ldc.i4.8
0x18902  ldstr    aChangepassword_10// "ChangePasswordButtonType"
0x18907  stelem.ref
0x18908  dup
0x18909  ldc.i4.s 9
0x1890b  ldstr    aChangepassword_6// "ChangePasswordTitleText"
0x18910  stelem.ref
0x18911  dup
0x18912  ldc.i4.s 0xA
0x18914  ldstr    aConfirmnewpass// "ConfirmNewPasswordLabelText"
0x18919  stelem.ref
0x1891a  dup
0x1891b  ldc.i4.s 0xB
0x1891d  ldstr    aConfirmpasswor// "ConfirmPasswordCompareErrorMessage"
0x18922  stelem.ref
0x18923  dup
0x18924  ldc.i4.s 0xC
0x18926  ldstr    aConfirmpasswor_0// "ConfirmPasswordRequiredErrorMessage"
0x1892b  stelem.ref
0x1892c  dup
0x1892d  ldc.i4.s 0xD
0x1892f  ldstr    aContinuebutton// "ContinueButtonImageUrl"
0x18934  stelem.ref
0x18935  dup
0x18936  ldc.i4.s 0xE
0x18938  ldstr    aContinuebutton_0// "ContinueButtonStyle"
0x1893d  stelem.ref
0x1893e  dup
0x1893f  ldc.i4.s 0xF
0x18941  ldstr    aContinuebutton_1// "ContinueButtonText"
0x18946  stelem.ref
0x18947  dup
0x18948  ldc.i4.s 0x10
0x1894a  ldstr    aContinuebutton_2// "ContinueButtonType"
0x1894f  stelem.ref
0x18950  dup
0x18951  ldc.i4.s 0x11
0x18953  ldstr    aCreateusericon// "CreateUserIconUrl"
0x18958  stelem.ref
0x18959  dup
0x1895a  ldc.i4.s 0x12
0x1895c  ldstr    aCreateusertext// "CreateUserText"
0x18961  stelem.ref
0x18962  dup
0x18963  ldc.i4.s 0x13
0x18965  ldstr    aCreateuserurl// "CreateUserUrl"
0x1896a  stelem.ref
0x1896b  dup
0x1896c  ldc.i4.s 0x14
0x1896e  ldstr    aDisplayusernam// "DisplayUserName"
0x18973  stelem.ref
0x18974  dup
0x18975  ldc.i4.s 0x15
0x18977  ldstr    aEditprofiletex// "EditProfileText"
0x1897c  stelem.ref
0x1897d  dup
0x1897e  ldc.i4.s 0x16
0x18980  ldstr    aEditprofileico// "EditProfileIconUrl"
0x18985  stelem.ref
0x18986  dup
0x18987  ldc.i4.s 0x17
0x18989  ldstr    aEditprofileurl// "EditProfileUrl"
0x1898e  stelem.ref
0x1898f  dup
0x18990  ldc.i4.s 0x18
0x18992  ldstr    aFailuretextsty// "FailureTextStyle"
0x18997  stelem.ref
0x18998  dup
0x18999  ldc.i4.s 0x19
0x1899b  ldstr    aHelppageiconur// "HelpPageIconUrl"
0x189a0  stelem.ref
0x189a1  dup
0x189a2  ldc.i4.s 0x1A
0x189a4  ldstr    aHelppagetext// "HelpPageText"
0x189a9  stelem.ref
0x189aa  dup
0x189ab  ldc.i4.s 0x1B
0x189ad  ldstr    aHelppageurl// "HelpPageUrl"
0x189b2  stelem.ref
0x189b3  dup
0x189b4  ldc.i4.s 0x1C
0x189b6  ldstr    aHyperlinkstyle// "HyperLinkStyle"
0x189bb  stelem.ref
0x189bc  dup
0x189bd  ldc.i4.s 0x1D
0x189bf  ldstr    aInstructiontex_1// "InstructionText"
0x189c4  stelem.ref
0x189c5  dup
0x189c6  ldc.i4.s 0x1E
0x189c8  ldstr    aInstructiontex_2// "InstructionTextStyle"
0x189cd  stelem.ref
0x189ce  dup
0x189cf  ldc.i4.s 0x1F
0x189d1  ldstr    aLabelstyle// "LabelStyle"
0x189d6  stelem.ref
0x189d7  dup
0x189d8  ldc.i4.s 0x20
0x189da  ldstr    aNewpasswordlab// "NewPasswordLabelText"
0x189df  stelem.ref
0x189e0  dup
0x189e1  ldc.i4.s 0x21
0x189e3  ldstr    aNewpasswordreq// "NewPasswordRequiredErrorMessage"
0x189e8  stelem.ref
0x189e9  dup
0x189ea  ldc.i4.s 0x22
0x189ec  ldstr    aNewpasswordreg// "NewPasswordRegularExpression"
0x189f1  stelem.ref
0x189f2  dup
0x189f3  ldc.i4.s 0x23
0x189f5  ldstr    aNewpasswordreg_0// "NewPasswordRegularExpressionErrorMessag"...
0x189fa  stelem.ref
0x189fb  dup
0x189fc  ldc.i4.s 0x24
0x189fe  ldstr    aPasswordhintte// "PasswordHintText"
0x18a03  stelem.ref
0x18a04  dup
0x18a05  ldc.i4.s 0x25
0x18a07  ldstr    aPasswordhintst// "PasswordHintStyle"
0x18a0c  stelem.ref
0x18a0d  dup
0x18a0e  ldc.i4.s 0x26
0x18a10  ldstr    aPasswordlabelt// "PasswordLabelText"
0x18a15  stelem.ref
0x18a16  dup
0x18a17  ldc.i4.s 0x27
0x18a19  ldstr    aPasswordrecove_5// "PasswordRecoveryText"
0x18a1e  stelem.ref
0x18a1f  dup
0x18a20  ldc.i4.s 0x28
0x18a22  ldstr    aPasswordrecove_6// "PasswordRecoveryUrl"
0x18a27  stelem.ref
0x18a28  dup
0x18a29  ldc.i4.s 0x29
0x18a2b  ldstr    aPasswordrecove_7// "PasswordRecoveryIconUrl"
0x18a30  stelem.ref
0x18a31  dup
0x18a32  ldc.i4.s 0x2A
0x18a34  ldstr    aPasswordrequir// "PasswordRequiredErrorMessage"
0x18a39  stelem.ref
0x18a3a  dup
0x18a3b  ldc.i4.s 0x2B
0x18a3d  ldstr    aSuccesstitlete// "SuccessTitleText"
0x18a42  stelem.ref
0x18a43  dup
0x18a44  ldc.i4.s 0x2C
0x18a46  ldstr    aSuccesstext// "SuccessText"
0x18a4b  stelem.ref
0x18a4c  dup
0x18a4d  ldc.i4.s 0x2D
0x18a4f  ldstr    aSuccesstextsty// "SuccessTextStyle"
0x18a54  stelem.ref
0x18a55  dup
0x18a56  ldc.i4.s 0x2E
0x18a58  ldstr    aTextboxstyle// "TextBoxStyle"
0x18a5d  stelem.ref
0x18a5e  dup
0x18a5f  ldc.i4.s 0x2F
0x18a61  ldstr    aTitletextstyle// "TitleTextStyle"
0x18a66  stelem.ref
0x18a67  dup
0x18a68  ldc.i4.s 0x30
0x18a6a  ldstr    aUsernamelabelt// "UserNameLabelText"
0x18a6f  stelem.ref
0x18a70  dup
0x18a71  ldc.i4.s 0x31
0x18a73  ldstr    aUsernamerequir// "UserNameRequiredErrorMessage"
0x18a78  stelem.ref
0x18a79  dup
0x18a7a  ldc.i4.s 0x32
0x18a7c  ldstr    aValidatortexts// "ValidatorTextStyle"
0x18a81  stelem.ref
0x18a82  stsfld   string[] System.Web.UI.Design.WebControls.ChangePasswordDesigner::_nonTemplateProperties
0x18a87  ret
```
