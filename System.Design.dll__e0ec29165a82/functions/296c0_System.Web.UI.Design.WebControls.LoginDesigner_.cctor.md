# System.Web.UI.Design.WebControls.LoginDesigner::.cctor

- ea: `0x296c0`
- end: `0x297e4`
- name: `System.Web.UI.Design.WebControls.LoginDesigner::.cctor`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x296d9`: `CreateUserIconUrl`
- `0x296e1`: `CreateUserText`
- `0x296e9`: `CreateUserUrl`
- `0x2971b`: `HyperLinkStyle`

## pseudocode

```c

```

## disassembly

```asm
0x296c0  ldc.i4.s 0x20
0x296c2  newarr   [mscorlib]System.String
0x296c7  dup
0x296c8  ldc.i4.0
0x296c9  ldstr    aBorderpadding// "BorderPadding"
0x296ce  stelem.ref
0x296cf  dup
0x296d0  ldc.i4.1
0x296d1  ldstr    aCheckboxstyle// "CheckBoxStyle"
0x296d6  stelem.ref
0x296d7  dup
0x296d8  ldc.i4.2
0x296d9  ldstr    aCreateusericon// "CreateUserIconUrl"
0x296de  stelem.ref
0x296df  dup
0x296e0  ldc.i4.3
0x296e1  ldstr    aCreateusertext// "CreateUserText"
0x296e6  stelem.ref
0x296e7  dup
0x296e8  ldc.i4.4
0x296e9  ldstr    aCreateuserurl// "CreateUserUrl"
0x296ee  stelem.ref
0x296ef  dup
0x296f0  ldc.i4.5
0x296f1  ldstr    aDisplayremembe// "DisplayRememberMe"
0x296f6  stelem.ref
0x296f7  dup
0x296f8  ldc.i4.6
0x296f9  ldstr    aFailuretextsty// "FailureTextStyle"
0x296fe  stelem.ref
0x296ff  dup
0x29700  ldc.i4.7
0x29701  ldstr    aHelppageiconur// "HelpPageIconUrl"
0x29706  stelem.ref
0x29707  dup
0x29708  ldc.i4.8
0x29709  ldstr    aHelppagetext// "HelpPageText"
0x2970e  stelem.ref
0x2970f  dup
0x29710  ldc.i4.s 9
0x29712  ldstr    aHelppageurl// "HelpPageUrl"
0x29717  stelem.ref
0x29718  dup
0x29719  ldc.i4.s 0xA
0x2971b  ldstr    aHyperlinkstyle// "HyperLinkStyle"
0x29720  stelem.ref
0x29721  dup
0x29722  ldc.i4.s 0xB
0x29724  ldstr    aInstructiontex_1// "InstructionText"
0x29729  stelem.ref
0x2972a  dup
0x2972b  ldc.i4.s 0xC
0x2972d  ldstr    aInstructiontex_2// "InstructionTextStyle"
0x29732  stelem.ref
0x29733  dup
0x29734  ldc.i4.s 0xD
0x29736  ldstr    aLabelstyle// "LabelStyle"
0x2973b  stelem.ref
0x2973c  dup
0x2973d  ldc.i4.s 0xE
0x2973f  ldstr    aOrientation// "Orientation"
0x29744  stelem.ref
0x29745  dup
0x29746  ldc.i4.s 0xF
0x29748  ldstr    aPasswordlabelt// "PasswordLabelText"
0x2974d  stelem.ref
0x2974e  dup
0x2974f  ldc.i4.s 0x10
0x29751  ldstr    aPasswordrecove_7// "PasswordRecoveryIconUrl"
0x29756  stelem.ref
0x29757  dup
0x29758  ldc.i4.s 0x11
0x2975a  ldstr    aPasswordrecove_5// "PasswordRecoveryText"
0x2975f  stelem.ref
0x29760  dup
0x29761  ldc.i4.s 0x12
0x29763  ldstr    aPasswordrecove_6// "PasswordRecoveryUrl"
0x29768  stelem.ref
0x29769  dup
0x2976a  ldc.i4.s 0x13
0x2976c  ldstr    aPasswordrequir// "PasswordRequiredErrorMessage"
0x29771  stelem.ref
0x29772  dup
0x29773  ldc.i4.s 0x14
0x29775  ldstr    aRemembermetext// "RememberMeText"
0x2977a  stelem.ref
0x2977b  dup
0x2977c  ldc.i4.s 0x15
0x2977e  ldstr    aLoginbuttonima// "LoginButtonImageUrl"
0x29783  stelem.ref
0x29784  dup
0x29785  ldc.i4.s 0x16
0x29787  ldstr    aLoginbuttonsty// "LoginButtonStyle"
0x2978c  stelem.ref
0x2978d  dup
0x2978e  ldc.i4.s 0x17
0x29790  ldstr    aLoginbuttontex// "LoginButtonText"
0x29795  stelem.ref
0x29796  dup
0x29797  ldc.i4.s 0x18
0x29799  ldstr    aLoginbuttontyp// "LoginButtonType"
0x2979e  stelem.ref
0x2979f  dup
0x297a0  ldc.i4.s 0x19
0x297a2  ldstr    aTextboxstyle// "TextBoxStyle"
0x297a7  stelem.ref
0x297a8  dup
0x297a9  ldc.i4.s 0x1A
0x297ab  ldstr    aTextlayout// "TextLayout"
0x297b0  stelem.ref
0x297b1  dup
0x297b2  ldc.i4.s 0x1B
0x297b4  ldstr    aTitletext// "TitleText"
0x297b9  stelem.ref
0x297ba  dup
0x297bb  ldc.i4.s 0x1C
0x297bd  ldstr    aTitletextstyle// "TitleTextStyle"
0x297c2  stelem.ref
0x297c3  dup
0x297c4  ldc.i4.s 0x1D
0x297c6  ldstr    aUsernamelabelt// "UserNameLabelText"
0x297cb  stelem.ref
0x297cc  dup
0x297cd  ldc.i4.s 0x1E
0x297cf  ldstr    aUsernamerequir// "UserNameRequiredErrorMessage"
0x297d4  stelem.ref
0x297d5  dup
0x297d6  ldc.i4.s 0x1F
0x297d8  ldstr    aValidatortexts// "ValidatorTextStyle"
0x297dd  stelem.ref
0x297de  stsfld   string[] System.Web.UI.Design.WebControls.LoginDesigner::_nonTemplateProperties
0x297e3  ret
```
