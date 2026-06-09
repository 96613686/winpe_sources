# System.Web.UI.Design.WebControls.PasswordRecoveryDesigner::.cctor

- ea: `0x32ee0`
- end: `0x33063`
- name: `System.Web.UI.Design.WebControls.PasswordRecoveryDesigner::.cctor`
- size: `387`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x32f61`: `SuccessTemplate`
- `0x32fad`: `HyperLinkStyle`
- `0x32f51`: `UserNameTemplate`
- `0x32f59`: `QuestionTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x32ee0  ldc.i4.3
0x32ee1  newarr   [mscorlib]System.String
0x32ee6  dup
0x32ee7  ldc.i4.0
0x32ee8  ldstr    aUsernamelabelt// "UserNameLabelText"
0x32eed  stelem.ref
0x32eee  dup
0x32eef  ldc.i4.1
0x32ef0  ldstr    aUsernametitlet// "UserNameTitleText"
0x32ef5  stelem.ref
0x32ef6  dup
0x32ef7  ldc.i4.2
0x32ef8  ldstr    aUsernameinstru// "UserNameInstructionText"
0x32efd  stelem.ref
0x32efe  stsfld   string[] System.Web.UI.Design.WebControls.PasswordRecoveryDesigner::_userNameViewRegionToPropertyMap
0x32f03  ldc.i4.5
0x32f04  newarr   [mscorlib]System.String
0x32f09  dup
0x32f0a  ldc.i4.0
0x32f0b  ldstr    aUsernamelabelt// "UserNameLabelText"
0x32f10  stelem.ref
0x32f11  dup
0x32f12  ldc.i4.1
0x32f13  ldstr    aQuestiontitlet// "QuestionTitleText"
0x32f18  stelem.ref
0x32f19  dup
0x32f1a  ldc.i4.2
0x32f1b  ldstr    aQuestionlabelt// "QuestionLabelText"
0x32f20  stelem.ref
0x32f21  dup
0x32f22  ldc.i4.3
0x32f23  ldstr    aQuestioninstru// "QuestionInstructionText"
0x32f28  stelem.ref
0x32f29  dup
0x32f2a  ldc.i4.4
0x32f2b  ldstr    aAnswerlabeltex// "AnswerLabelText"
0x32f30  stelem.ref
0x32f31  stsfld   string[] System.Web.UI.Design.WebControls.PasswordRecoveryDesigner::_questionViewRegionToPropertyMap
0x32f36  ldc.i4.1
0x32f37  newarr   [mscorlib]System.String
0x32f3c  dup
0x32f3d  ldc.i4.0
0x32f3e  ldstr    aSuccesstext// "SuccessText"
0x32f43  stelem.ref
0x32f44  stsfld   string[] System.Web.UI.Design.WebControls.PasswordRecoveryDesigner::_successViewRegionToPropertyMap
0x32f49  ldc.i4.3
0x32f4a  newarr   [mscorlib]System.String
0x32f4f  dup
0x32f50  ldc.i4.0
0x32f51  ldstr    aUsernametempla// "UserNameTemplate"
0x32f56  stelem.ref
0x32f57  dup
0x32f58  ldc.i4.1
0x32f59  ldstr    aQuestiontempla// "QuestionTemplate"
0x32f5e  stelem.ref
0x32f5f  dup
0x32f60  ldc.i4.2
0x32f61  ldstr    aSuccesstemplat// "SuccessTemplate"
0x32f66  stelem.ref
0x32f67  stsfld   string[] System.Web.UI.Design.WebControls.PasswordRecoveryDesigner::_templateNames
0x32f6c  ldc.i4.s 0x1B
0x32f6e  newarr   [mscorlib]System.String
0x32f73  dup
0x32f74  ldc.i4.0
0x32f75  ldstr    aAnswerlabeltex// "AnswerLabelText"
0x32f7a  stelem.ref
0x32f7b  dup
0x32f7c  ldc.i4.1
0x32f7d  ldstr    aAnswerrequired_0// "AnswerRequiredErrorMessage"
0x32f82  stelem.ref
0x32f83  dup
0x32f84  ldc.i4.2
0x32f85  ldstr    aBorderpadding// "BorderPadding"
0x32f8a  stelem.ref
0x32f8b  dup
0x32f8c  ldc.i4.3
0x32f8d  ldstr    aHelppageiconur// "HelpPageIconUrl"
0x32f92  stelem.ref
0x32f93  dup
0x32f94  ldc.i4.4
0x32f95  ldstr    aFailuretextsty// "FailureTextStyle"
0x32f9a  stelem.ref
0x32f9b  dup
0x32f9c  ldc.i4.5
0x32f9d  ldstr    aHelppagetext// "HelpPageText"
0x32fa2  stelem.ref
0x32fa3  dup
0x32fa4  ldc.i4.6
0x32fa5  ldstr    aHelppageurl// "HelpPageUrl"
0x32faa  stelem.ref
0x32fab  dup
0x32fac  ldc.i4.7
0x32fad  ldstr    aHyperlinkstyle// "HyperLinkStyle"
0x32fb2  stelem.ref
0x32fb3  dup
0x32fb4  ldc.i4.8
0x32fb5  ldstr    aInstructiontex_2// "InstructionTextStyle"
0x32fba  stelem.ref
0x32fbb  dup
0x32fbc  ldc.i4.s 9
0x32fbe  ldstr    aLabelstyle// "LabelStyle"
0x32fc3  stelem.ref
0x32fc4  dup
0x32fc5  ldc.i4.s 0xA
0x32fc7  ldstr    aQuestioninstru// "QuestionInstructionText"
0x32fcc  stelem.ref
0x32fcd  dup
0x32fce  ldc.i4.s 0xB
0x32fd0  ldstr    aQuestionlabelt// "QuestionLabelText"
0x32fd5  stelem.ref
0x32fd6  dup
0x32fd7  ldc.i4.s 0xC
0x32fd9  ldstr    aQuestiontitlet// "QuestionTitleText"
0x32fde  stelem.ref
0x32fdf  dup
0x32fe0  ldc.i4.s 0xD
0x32fe2  ldstr    aSubmitbuttonim// "SubmitButtonImageUrl"
0x32fe7  stelem.ref
0x32fe8  dup
0x32fe9  ldc.i4.s 0xE
0x32feb  ldstr    aSubmitbuttonst// "SubmitButtonStyle"
0x32ff0  stelem.ref
0x32ff1  dup
0x32ff2  ldc.i4.s 0xF
0x32ff4  ldstr    aSubmitbuttonte// "SubmitButtonText"
0x32ff9  stelem.ref
0x32ffa  dup
0x32ffb  ldc.i4.s 0x10
0x32ffd  ldstr    aSubmitbuttonty// "SubmitButtonType"
0x33002  stelem.ref
0x33003  dup
0x33004  ldc.i4.s 0x11
0x33006  ldstr    aSuccesstext// "SuccessText"
0x3300b  stelem.ref
0x3300c  dup
0x3300d  ldc.i4.s 0x12
0x3300f  ldstr    aSuccesstextsty// "SuccessTextStyle"
0x33014  stelem.ref
0x33015  dup
0x33016  ldc.i4.s 0x13
0x33018  ldstr    aTextboxstyle// "TextBoxStyle"
0x3301d  stelem.ref
0x3301e  dup
0x3301f  ldc.i4.s 0x14
0x33021  ldstr    aTextlayout// "TextLayout"
0x33026  stelem.ref
0x33027  dup
0x33028  ldc.i4.s 0x15
0x3302a  ldstr    aTitletextstyle// "TitleTextStyle"
0x3302f  stelem.ref
0x33030  dup
0x33031  ldc.i4.s 0x16
0x33033  ldstr    aUsernameinstru// "UserNameInstructionText"
0x33038  stelem.ref
0x33039  dup
0x3303a  ldc.i4.s 0x17
0x3303c  ldstr    aUsernamelabelt// "UserNameLabelText"
0x33041  stelem.ref
0x33042  dup
0x33043  ldc.i4.s 0x18
0x33045  ldstr    aUsernamerequir// "UserNameRequiredErrorMessage"
0x3304a  stelem.ref
0x3304b  dup
0x3304c  ldc.i4.s 0x19
0x3304e  ldstr    aUsernametitlet// "UserNameTitleText"
0x33053  stelem.ref
0x33054  dup
0x33055  ldc.i4.s 0x1A
0x33057  ldstr    aValidatortexts// "ValidatorTextStyle"
0x3305c  stelem.ref
0x3305d  stsfld   string[] System.Web.UI.Design.WebControls.PasswordRecoveryDesigner::_nonTemplateProperties
0x33062  ret
```
