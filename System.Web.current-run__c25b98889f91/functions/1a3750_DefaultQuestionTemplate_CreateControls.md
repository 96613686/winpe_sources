# DefaultQuestionTemplate::CreateControls

- ea: `0x1a3750`
- end: `0x1a3910`
- name: `DefaultQuestionTemplate::CreateControls`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `44`
- tags: ``

## callers

- `0x1a3fc0`

## callees

- `0x34fa0`
- `0x5f1b0`
- `0x5f1e0`
- `0x5fc20`
- `0x5fc90`
- `0x916b0`
- `0x91820`
- `0x918e0`
- `0x936b0`
- `0x93730`
- `0x93900`
- `0xb9930`
- `0xbaf70`
- `0xbb320`
- `0xbb360`
- `0xbb560`
- `0xbcd00`
- `0xbcea0`
- `0xbd090`
- `0xbd0d0`
- `0xbd2e0`
- `0xbf6d0`
- `0xd1610`
- `0xd70e0`
- `0xdf2c0`
- `0xea6f0`
- `0x1a47f0`
- `0x1a4810`
- `0x1a4840`
- `0x1a4880`
- `0x1a48a0`
- `0x1a48b0`
- `0x1a48c0`
- `0x1a48e0`
- `0x1a4900`
- `0x1a4920`
- `0x1a4940`
- `0x1a4950`
- `0x1a4970`
- `0x1a4990`
- `0x1a49b0`
- `0x1a49c0`
- `0x1a49e0`
- `0x1a4a00`

## string_xrefs

- `0x1a38df`: `HelpLink`
- `0x1a384a`: `SubmitLinkButton`

## pseudocode

```c

```

## disassembly

```asm
0x1a3750  ldarg.0
0x1a3751  ldfld    class System.Web.UI.WebControls.PasswordRecovery DefaultQuestionTemplate::_owner
0x1a3756  callvirt instance string System.Web.UI.Control::get_UniqueID()
0x1a375b  stloc.0
0x1a375c  ldarg.1
0x1a375d  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x1a3762  callvirt instance void QuestionContainer::set_Title(class System.Web.UI.WebControls.Literal value)
0x1a3767  ldarg.1
0x1a3768  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x1a376d  callvirt instance void QuestionContainer::set_Instruction(class System.Web.UI.WebControls.Literal value)
0x1a3772  ldarg.1
0x1a3773  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x1a3778  callvirt instance void QuestionContainer::set_UserNameLabel(class System.Web.UI.WebControls.Literal value)
0x1a377d  ldarg.1
0x1a377e  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x1a3783  callvirt instance void QuestionContainer::set_UserName(class System.Web.UI.Control value)
0x1a3788  ldarg.1
0x1a3789  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x1a378e  callvirt instance void QuestionContainer::set_QuestionLabel(class System.Web.UI.WebControls.Literal value)
0x1a3793  ldarg.1
0x1a3794  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x1a3799  callvirt instance void QuestionContainer::set_Question(class System.Web.UI.Control value)
0x1a379e  ldarg.1
0x1a379f  callvirt instance class System.Web.UI.Control QuestionContainer::get_UserName()
0x1a37a4  ldstr    aUsername// "UserName"
0x1a37a9  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x1a37ae  ldarg.1
0x1a37af  callvirt instance class System.Web.UI.Control QuestionContainer::get_Question()
0x1a37b4  ldstr    aQuestion// "Question"
0x1a37b9  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x1a37be  newobj   instance void System.Web.UI.WebControls.TextBox::.ctor()
0x1a37c3  stloc.1
0x1a37c4  ldloc.1
0x1a37c5  ldstr    aAnswer// "Answer"
0x1a37ca  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x1a37cf  ldarg.1
0x1a37d0  ldloc.1
0x1a37d1  callvirt instance void QuestionContainer::set_AnswerTextBox(class System.Web.UI.Control value)
0x1a37d6  ldarg.1
0x1a37d7  ldloc.1
0x1a37d8  newobj   instance void System.Web.UI.WebControls.LabelLiteral::.ctor(class System.Web.UI.Control forControl)
0x1a37dd  callvirt instance void QuestionContainer::set_AnswerLabel(class System.Web.UI.WebControls.LabelLiteral value)
0x1a37e2  ldarg.0
0x1a37e3  ldfld    class System.Web.UI.WebControls.PasswordRecovery DefaultQuestionTemplate::_owner
0x1a37e8  callvirt instance valuetype View System.Web.UI.WebControls.PasswordRecovery::get_CurrentView()
0x1a37ed  ldc.i4.1
0x1a37ee  ceq
0x1a37f0  stloc.2
0x1a37f1  newobj   instance void System.Web.UI.WebControls.RequiredFieldValidator::.ctor()
0x1a37f6  stloc.3
0x1a37f7  ldloc.3
0x1a37f8  ldstr    aAnswerrequired_0// "AnswerRequired"
0x1a37fd  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x1a3802  ldloc.3
0x1a3803  ldloc.0
0x1a3804  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ValidationGroup(string value)
0x1a3809  ldloc.3
0x1a380a  ldloc.1
0x1a380b  callvirt instance string System.Web.UI.Control::get_ID()
0x1a3810  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ControlToValidate(string value)
0x1a3815  ldloc.3
0x1a3816  ldc.i4.1
0x1a3817  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_Display(valuetype System.Web.UI.WebControls.ValidatorDisplay value)
0x1a381c  ldloc.3
0x1a381d  ldstr    aLogincontrolsD_0// "LoginControls_DefaultRequiredFieldValid"...
0x1a3822  call     string System.Web.SR::GetString(string name)
0x1a3827  callvirt instance void System.Web.UI.WebControls.Label::set_Text(string value)
0x1a382c  ldloc.3
0x1a382d  ldloc.2
0x1a382e  callvirt instance void System.Web.UI.WebControls.WebControl::set_Enabled(bool value)
0x1a3833  ldloc.3
0x1a3834  ldloc.2
0x1a3835  callvirt instance void System.Web.UI.Control::set_Visible(bool value)
0x1a383a  ldarg.1
0x1a383b  ldloc.3
0x1a383c  callvirt instance void QuestionContainer::set_AnswerRequired(class System.Web.UI.WebControls.RequiredFieldValidator value)
0x1a3841  newobj   instance void System.Web.UI.WebControls.LinkButton::.ctor()
0x1a3846  stloc.s  4
0x1a3848  ldloc.s  4
0x1a384a  ldstr    aSubmitlinkbutt// "SubmitLinkButton"
0x1a384f  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x1a3854  ldloc.s  4
0x1a3856  ldloc.0
0x1a3857  callvirt instance void System.Web.UI.WebControls.LinkButton::set_ValidationGroup(string value)
0x1a385c  ldloc.s  4
0x1a385e  ldsfld   string System.Web.UI.WebControls.PasswordRecovery::SubmitButtonCommandName
0x1a3863  callvirt instance void System.Web.UI.WebControls.LinkButton::set_CommandName(string value)
0x1a3868  ldarg.1
0x1a3869  ldloc.s  4
0x1a386b  callvirt instance void QuestionContainer::set_LinkButton(class System.Web.UI.WebControls.LinkButton value)
0x1a3870  newobj   instance void System.Web.UI.WebControls.ImageButton::.ctor()
0x1a3875  stloc.s  5
0x1a3877  ldloc.s  5
0x1a3879  ldstr    aSubmitimagebut// "SubmitImageButton"
0x1a387e  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x1a3883  ldloc.s  5
0x1a3885  ldloc.0
0x1a3886  callvirt instance void System.Web.UI.WebControls.ImageButton::set_ValidationGroup(string value)
0x1a388b  ldloc.s  5
0x1a388d  ldsfld   string System.Web.UI.WebControls.PasswordRecovery::SubmitButtonCommandName
0x1a3892  callvirt instance void System.Web.UI.WebControls.ImageButton::set_CommandName(string value)
0x1a3897  ldarg.1
0x1a3898  ldloc.s  5
0x1a389a  callvirt instance void QuestionContainer::set_ImageButton(class System.Web.UI.WebControls.ImageButton value)
0x1a389f  newobj   instance void System.Web.UI.WebControls.Button::.ctor()
0x1a38a4  stloc.s  6
0x1a38a6  ldloc.s  6
0x1a38a8  ldstr    aSubmitbutton// "SubmitButton"
0x1a38ad  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x1a38b2  ldloc.s  6
0x1a38b4  ldloc.0
0x1a38b5  callvirt instance void System.Web.UI.WebControls.Button::set_ValidationGroup(string value)
0x1a38ba  ldloc.s  6
0x1a38bc  ldsfld   string System.Web.UI.WebControls.PasswordRecovery::SubmitButtonCommandName
0x1a38c1  callvirt instance void System.Web.UI.WebControls.Button::set_CommandName(string value)
0x1a38c6  ldarg.1
0x1a38c7  ldloc.s  6
0x1a38c9  callvirt instance void QuestionContainer::set_PushButton(class System.Web.UI.WebControls.Button value)
0x1a38ce  ldarg.1
0x1a38cf  newobj   instance void System.Web.UI.WebControls.HyperLink::.ctor()
0x1a38d4  callvirt instance void QuestionContainer::set_HelpPageLink(class System.Web.UI.WebControls.HyperLink value)
0x1a38d9  ldarg.1
0x1a38da  callvirt instance class System.Web.UI.WebControls.HyperLink QuestionContainer::get_HelpPageLink()
0x1a38df  ldstr    aHelplink// "HelpLink"
0x1a38e4  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x1a38e9  ldarg.1
0x1a38ea  newobj   instance void System.Web.UI.WebControls.Image::.ctor()
0x1a38ef  callvirt instance void QuestionContainer::set_HelpPageIcon(class System.Web.UI.WebControls.Image value)
0x1a38f4  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x1a38f9  stloc.s  7
0x1a38fb  ldloc.s  7
0x1a38fd  ldstr    aFailuretext// "FailureText"
0x1a3902  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x1a3907  ldarg.1
0x1a3908  ldloc.s  7
0x1a390a  callvirt instance void QuestionContainer::set_FailureTextLabel(class System.Web.UI.Control value)
0x1a390f  ret
```
