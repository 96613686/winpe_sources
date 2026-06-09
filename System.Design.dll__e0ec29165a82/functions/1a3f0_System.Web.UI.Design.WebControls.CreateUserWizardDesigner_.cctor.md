# System.Web.UI.Design.WebControls.CreateUserWizardDesigner::.cctor

- ea: `0x1a3f0`
- end: `0x1a76f`
- name: `System.Web.UI.Design.WebControls.CreateUserWizardDesigner::.cctor`
- size: `895`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## string_xrefs

- `0x1a4dc`: `ConfirmPasswordCompareErrorMessage`
- `0x1a515`: `HyperLinkStyle`
- `0x1a46f`: `PasswordCompare`
- `0x1a49c`: `HelpLink`
- `0x1a4a5`: `EditProfileLink`
- `0x1a5f3`: `CreateUserButtonImageUrl`
- `0x1a5fb`: `CreateUserButtonType`
- `0x1a603`: `CreateUserButtonStyle`
- `0x1a60b`: `CreateUserButtonText`
- `0x1a61f`: `CompleteSuccessText`
- `0x1a627`: `CompleteSuccessTextStyle`
- `0x1a6a1`: `CancelButtonLinkButton`
- `0x1a6dd`: `StepNextButtonLinkButton`
- `0x1a719`: `StepPreviousButtonLinkButton`
- `0x1a75f`: `ContinueButtonLinkButton`

## pseudocode

```c

```

## disassembly

```asm
0x1a3f0  ldc.i4.s 0x15
0x1a3f2  newarr   [mscorlib]System.String
0x1a3f7  dup
0x1a3f8  ldc.i4.0
0x1a3f9  ldstr    aUsername// "UserName"
0x1a3fe  stelem.ref
0x1a3ff  dup
0x1a400  ldc.i4.1
0x1a401  ldstr    aUsernamerequir_0// "UserNameRequired"
0x1a406  stelem.ref
0x1a407  dup
0x1a408  ldc.i4.2
0x1a409  ldstr    aPassword// "Password"
0x1a40e  stelem.ref
0x1a40f  dup
0x1a410  ldc.i4.3
0x1a411  ldstr    aPasswordrequir_0// "PasswordRequired"
0x1a416  stelem.ref
0x1a417  dup
0x1a418  ldc.i4.4
0x1a419  ldstr    aConfirmpasswor_1// "ConfirmPassword"
0x1a41e  stelem.ref
0x1a41f  dup
0x1a420  ldc.i4.5
0x1a421  ldstr    aEmail// "Email"
0x1a426  stelem.ref
0x1a427  dup
0x1a428  ldc.i4.6
0x1a429  ldstr    aQuestion// "Question"
0x1a42e  stelem.ref
0x1a42f  dup
0x1a430  ldc.i4.7
0x1a431  ldstr    aAnswer// "Answer"
0x1a436  stelem.ref
0x1a437  dup
0x1a438  ldc.i4.8
0x1a439  ldstr    aConfirmpasswor_2// "ConfirmPasswordRequired"
0x1a43e  stelem.ref
0x1a43f  dup
0x1a440  ldc.i4.s 9
0x1a442  ldstr    aPasswordregexp// "PasswordRegExp"
0x1a447  stelem.ref
0x1a448  dup
0x1a449  ldc.i4.s 0xA
0x1a44b  ldstr    aEmailregexp// "EmailRegExp"
0x1a450  stelem.ref
0x1a451  dup
0x1a452  ldc.i4.s 0xB
0x1a454  ldstr    aEmailrequired// "EmailRequired"
0x1a459  stelem.ref
0x1a45a  dup
0x1a45b  ldc.i4.s 0xC
0x1a45d  ldstr    aQuestionrequir// "QuestionRequired"
0x1a462  stelem.ref
0x1a463  dup
0x1a464  ldc.i4.s 0xD
0x1a466  ldstr    aAnswerrequired// "AnswerRequired"
0x1a46b  stelem.ref
0x1a46c  dup
0x1a46d  ldc.i4.s 0xE
0x1a46f  ldstr    aPasswordcompar// "PasswordCompare"
0x1a474  stelem.ref
0x1a475  dup
0x1a476  ldc.i4.s 0xF
0x1a478  ldstr    aCancelbutton_0// "CancelButton"
0x1a47d  stelem.ref
0x1a47e  dup
0x1a47f  ldc.i4.s 0x10
0x1a481  ldstr    aContinuebutton_3// "ContinueButton"
0x1a486  stelem.ref
0x1a487  dup
0x1a488  ldc.i4.s 0x11
0x1a48a  ldstr    aStepnextbutton// "StepNextButton"
0x1a48f  stelem.ref
0x1a490  dup
0x1a491  ldc.i4.s 0x12
0x1a493  ldstr    aErrormessage// "ErrorMessage"
0x1a498  stelem.ref
0x1a499  dup
0x1a49a  ldc.i4.s 0x13
0x1a49c  ldstr    aHelplink// "HelpLink"
0x1a4a1  stelem.ref
0x1a4a2  dup
0x1a4a3  ldc.i4.s 0x14
0x1a4a5  ldstr    aEditprofilelin// "EditProfileLink"
0x1a4aa  stelem.ref
0x1a4ab  stsfld   string[] System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_persistedControlIDs
0x1a4b0  ldc.i4.1
0x1a4b1  newarr   [mscorlib]System.String
0x1a4b6  dup
0x1a4b7  ldc.i4.0
0x1a4b8  ldstr    aErrormessage// "ErrorMessage"
0x1a4bd  stelem.ref
0x1a4be  stsfld   string[] System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_persistedIfNotVisibleControlIDs
0x1a4c3  ldc.i4.s 0x1D
0x1a4c5  newarr   [mscorlib]System.String
0x1a4ca  dup
0x1a4cb  ldc.i4.0
0x1a4cc  ldstr    aAnswerlabeltex// "AnswerLabelText"
0x1a4d1  stelem.ref
0x1a4d2  dup
0x1a4d3  ldc.i4.1
0x1a4d4  ldstr    aConfirmpasswor_3// "ConfirmPasswordLabelText"
0x1a4d9  stelem.ref
0x1a4da  dup
0x1a4db  ldc.i4.2
0x1a4dc  ldstr    aConfirmpasswor// "ConfirmPasswordCompareErrorMessage"
0x1a4e1  stelem.ref
0x1a4e2  dup
0x1a4e3  ldc.i4.3
0x1a4e4  ldstr    aConfirmpasswor_0// "ConfirmPasswordRequiredErrorMessage"
0x1a4e9  stelem.ref
0x1a4ea  dup
0x1a4eb  ldc.i4.4
0x1a4ec  ldstr    aEmaillabeltext// "EmailLabelText"
0x1a4f1  stelem.ref
0x1a4f2  dup
0x1a4f3  ldc.i4.5
0x1a4f4  ldstr    aErrormessagest// "ErrorMessageStyle"
0x1a4f9  stelem.ref
0x1a4fa  dup
0x1a4fb  ldc.i4.6
0x1a4fc  ldstr    aHelppageiconur// "HelpPageIconUrl"
0x1a501  stelem.ref
0x1a502  dup
0x1a503  ldc.i4.7
0x1a504  ldstr    aHelppagetext// "HelpPageText"
0x1a509  stelem.ref
0x1a50a  dup
0x1a50b  ldc.i4.8
0x1a50c  ldstr    aHelppageurl// "HelpPageUrl"
0x1a511  stelem.ref
0x1a512  dup
0x1a513  ldc.i4.s 9
0x1a515  ldstr    aHyperlinkstyle// "HyperLinkStyle"
0x1a51a  stelem.ref
0x1a51b  dup
0x1a51c  ldc.i4.s 0xA
0x1a51e  ldstr    aInstructiontex_1// "InstructionText"
0x1a523  stelem.ref
0x1a524  dup
0x1a525  ldc.i4.s 0xB
0x1a527  ldstr    aInstructiontex_2// "InstructionTextStyle"
0x1a52c  stelem.ref
0x1a52d  dup
0x1a52e  ldc.i4.s 0xC
0x1a530  ldstr    aLabelstyle// "LabelStyle"
0x1a535  stelem.ref
0x1a536  dup
0x1a537  ldc.i4.s 0xD
0x1a539  ldstr    aPasswordhintte// "PasswordHintText"
0x1a53e  stelem.ref
0x1a53f  dup
0x1a540  ldc.i4.s 0xE
0x1a542  ldstr    aPasswordhintst// "PasswordHintStyle"
0x1a547  stelem.ref
0x1a548  dup
0x1a549  ldc.i4.s 0xF
0x1a54b  ldstr    aPasswordlabelt// "PasswordLabelText"
0x1a550  stelem.ref
0x1a551  dup
0x1a552  ldc.i4.s 0x10
0x1a554  ldstr    aPasswordrequir// "PasswordRequiredErrorMessage"
0x1a559  stelem.ref
0x1a55a  dup
0x1a55b  ldc.i4.s 0x11
0x1a55d  ldstr    aQuestionlabelt// "QuestionLabelText"
0x1a562  stelem.ref
0x1a563  dup
0x1a564  ldc.i4.s 0x12
0x1a566  ldstr    aTextboxstyle// "TextBoxStyle"
0x1a56b  stelem.ref
0x1a56c  dup
0x1a56d  ldc.i4.s 0x13
0x1a56f  ldstr    aUsernamelabelt// "UserNameLabelText"
0x1a574  stelem.ref
0x1a575  dup
0x1a576  ldc.i4.s 0x14
0x1a578  ldstr    aUsernamerequir// "UserNameRequiredErrorMessage"
0x1a57d  stelem.ref
0x1a57e  dup
0x1a57f  ldc.i4.s 0x15
0x1a581  ldstr    aAnswerrequired_0// "AnswerRequiredErrorMessage"
0x1a586  stelem.ref
0x1a587  dup
0x1a588  ldc.i4.s 0x16
0x1a58a  ldstr    aEmailregularex// "EmailRegularExpression"
0x1a58f  stelem.ref
0x1a590  dup
0x1a591  ldc.i4.s 0x17
0x1a593  ldstr    aEmailregularex_0// "EmailRegularExpressionErrorMessage"
0x1a598  stelem.ref
0x1a599  dup
0x1a59a  ldc.i4.s 0x18
0x1a59c  ldstr    aEmailrequirede// "EmailRequiredErrorMessage"
0x1a5a1  stelem.ref
0x1a5a2  dup
0x1a5a3  ldc.i4.s 0x19
0x1a5a5  ldstr    aPasswordregula// "PasswordRegularExpression"
0x1a5aa  stelem.ref
0x1a5ab  dup
0x1a5ac  ldc.i4.s 0x1A
0x1a5ae  ldstr    aPasswordregula_0// "PasswordRegularExpressionErrorMessage"
0x1a5b3  stelem.ref
0x1a5b4  dup
0x1a5b5  ldc.i4.s 0x1B
0x1a5b7  ldstr    aQuestionrequir_0// "QuestionRequiredErrorMessage"
0x1a5bc  stelem.ref
0x1a5bd  dup
0x1a5be  ldc.i4.s 0x1C
0x1a5c0  ldstr    aValidatortexts// "ValidatorTextStyle"
0x1a5c5  stelem.ref
0x1a5c6  stsfld   string[] System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_defaultCreateStepProperties
0x1a5cb  ldc.i4.8
0x1a5cc  newarr   [mscorlib]System.String
0x1a5d1  dup
0x1a5d2  ldc.i4.0
0x1a5d3  ldstr    aCancelbuttonim// "CancelButtonImageUrl"
0x1a5d8  stelem.ref
0x1a5d9  dup
0x1a5da  ldc.i4.1
0x1a5db  ldstr    aCancelbuttonty// "CancelButtonType"
0x1a5e0  stelem.ref
0x1a5e1  dup
0x1a5e2  ldc.i4.2
0x1a5e3  ldstr    aCancelbuttonst// "CancelButtonStyle"
0x1a5e8  stelem.ref
0x1a5e9  dup
0x1a5ea  ldc.i4.3
0x1a5eb  ldstr    aCancelbuttonte// "CancelButtonText"
0x1a5f0  stelem.ref
0x1a5f1  dup
0x1a5f2  ldc.i4.4
0x1a5f3  ldstr    aCreateuserbutt// "CreateUserButtonImageUrl"
0x1a5f8  stelem.ref
0x1a5f9  dup
0x1a5fa  ldc.i4.5
0x1a5fb  ldstr    aCreateuserbutt_0// "CreateUserButtonType"
0x1a600  stelem.ref
0x1a601  dup
0x1a602  ldc.i4.6
0x1a603  ldstr    aCreateuserbutt_1// "CreateUserButtonStyle"
0x1a608  stelem.ref
0x1a609  dup
0x1a60a  ldc.i4.7
0x1a60b  ldstr    aCreateuserbutt_2// "CreateUserButtonText"
0x1a610  stelem.ref
0x1a611  stsfld   string[] System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_defaultCreateUserNavProperties
0x1a616  ldc.i4.s 9
0x1a618  newarr   [mscorlib]System.String
0x1a61d  dup
0x1a61e  ldc.i4.0
0x1a61f  ldstr    aCompletesucces// "CompleteSuccessText"
0x1a624  stelem.ref
0x1a625  dup
0x1a626  ldc.i4.1
0x1a627  ldstr    aCompletesucces_0// "CompleteSuccessTextStyle"
0x1a62c  stelem.ref
0x1a62d  dup
0x1a62e  ldc.i4.2
0x1a62f  ldstr    aContinuebutton_0// "ContinueButtonStyle"
0x1a634  stelem.ref
0x1a635  dup
0x1a636  ldc.i4.3
0x1a637  ldstr    aContinuebutton_1// "ContinueButtonText"
0x1a63c  stelem.ref
0x1a63d  dup
0x1a63e  ldc.i4.4
0x1a63f  ldstr    aContinuebutton_2// "ContinueButtonType"
0x1a644  stelem.ref
0x1a645  dup
0x1a646  ldc.i4.5
0x1a647  ldstr    aContinuebutton// "ContinueButtonImageUrl"
0x1a64c  stelem.ref
0x1a64d  dup
0x1a64e  ldc.i4.6
0x1a64f  ldstr    aEditprofiletex// "EditProfileText"
0x1a654  stelem.ref
0x1a655  dup
0x1a656  ldc.i4.7
0x1a657  ldstr    aEditprofileico// "EditProfileIconUrl"
0x1a65c  stelem.ref
0x1a65d  dup
0x1a65e  ldc.i4.8
0x1a65f  ldstr    aEditprofileurl// "EditProfileUrl"
0x1a664  stelem.ref
0x1a665  stsfld   string[] System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_defaultCompleteStepProperties
0x1a66a  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x1a66f  stsfld   class [mscorlib]System.Collections.Hashtable System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_persistedIDConverter
0x1a674  ldsfld   class [mscorlib]System.Collections.Hashtable System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_persistedIDConverter
0x1a679  ldstr    aCancelbuttonim_0// "CancelButtonImageButton"
0x1a67e  ldstr    aCancelbutton_0// "CancelButton"
0x1a683  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x1a688  ldsfld   class [mscorlib]System.Collections.Hashtable System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_persistedIDConverter
0x1a68d  ldstr    aCancelbuttonbu// "CancelButtonButton"
0x1a692  ldstr    aCancelbutton_0// "CancelButton"
0x1a697  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x1a69c  ldsfld   class [mscorlib]System.Collections.Hashtable System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_persistedIDConverter
0x1a6a1  ldstr    aCancelbuttonli// "CancelButtonLinkButton"
0x1a6a6  ldstr    aCancelbutton_0// "CancelButton"
  ... truncated ...
```
