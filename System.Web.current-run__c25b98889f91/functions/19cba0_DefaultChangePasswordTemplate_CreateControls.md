# DefaultChangePasswordTemplate::CreateControls

- ea: `0x19cba0`
- end: `0x19cfa4`
- name: `DefaultChangePasswordTemplate::CreateControls`
- size: `1028`
- prototype: ``
- caller_count: `1`
- callee_count: `76`
- tags: `file_ops, broker_com_uri`

## callers

- `0x19d5e0`

## callees

- `0x5f1e0`
- `0x5fc20`
- `0x5fc90`
- `0x6e540`
- `0x916b0`
- `0x91700`
- `0x91820`
- `0x918e0`
- `0x936b0`
- `0x936e0`
- `0x93730`
- `0x93900`
- `0x96fe0`
- `0x97360`
- `0x97790`
- `0x97830`
- `0x9c720`
- `0x9c760`
- `0x9ca60`
- `0xb9930`
- `0xbaf70`
- `0xbb320`
- `0xbb360`
- `0xbb3f0`
- `0xbb560`
- `0xbcea0`
- `0xbd090`
- `0xbd0d0`
- `0xbd160`
- `0xbd2e0`
- `0xbf6d0`
- `0xd5450`
- `0xd5580`
- `0xdf2c0`
- `0xdf460`
- `0xea6f0`
- `0x19cb50`
- `0x19d670`
- `0x19d690`
- `0x19d6b0`
- `0x19d6d0`
- `0x19d6f0`
- `0x19d710`
- `0x19d730`
- `0x19d750`
- `0x19d780`
- `0x19d7b0`
- `0x19d7c0`
- `0x19d7d0`
- `0x19d7f0`

## string_xrefs

- `0x19cce6`: `NewPasswordCompare`
- `0x19cdbe`: `ChangePasswordLinkButton`
- `0x19cded`: `CancelLinkButton`
- `0x19ceeb`: `PasswordRecoveryLink`
- `0x19cf11`: `CreateUserLink`
- `0x19cf42`: `HelpLink`
- `0x19cf68`: `EditProfileLink`

## pseudocode

```c

```

## disassembly

```asm
0x19cba0  ldarg.0
0x19cba1  ldfld    class System.Web.UI.WebControls.ChangePassword DefaultChangePasswordTemplate::_owner
0x19cba6  callvirt instance string System.Web.UI.Control::get_UniqueID()
0x19cbab  stloc.0
0x19cbac  ldarg.1
0x19cbad  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x19cbb2  callvirt instance void ChangePasswordContainer::set_Title(class System.Web.UI.WebControls.Literal value)
0x19cbb7  ldarg.1
0x19cbb8  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x19cbbd  callvirt instance void ChangePasswordContainer::set_Instruction(class System.Web.UI.WebControls.Literal value)
0x19cbc2  ldarg.1
0x19cbc3  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x19cbc8  callvirt instance void ChangePasswordContainer::set_PasswordHintLabel(class System.Web.UI.WebControls.Literal value)
0x19cbcd  newobj   instance void System.Web.UI.WebControls.TextBox::.ctor()
0x19cbd2  stloc.1
0x19cbd3  ldloc.1
0x19cbd4  ldstr    aUsername// "UserName"
0x19cbd9  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19cbde  ldarg.1
0x19cbdf  ldloc.1
0x19cbe0  callvirt instance void ChangePasswordContainer::set_UserNameTextBox(class System.Web.UI.Control value)
0x19cbe5  ldarg.1
0x19cbe6  ldloc.1
0x19cbe7  newobj   instance void System.Web.UI.WebControls.LabelLiteral::.ctor(class System.Web.UI.Control forControl)
0x19cbec  callvirt instance void ChangePasswordContainer::set_UserNameLabel(class System.Web.UI.WebControls.LabelLiteral value)
0x19cbf1  ldarg.0
0x19cbf2  ldfld    class System.Web.UI.WebControls.ChangePassword DefaultChangePasswordTemplate::_owner
0x19cbf7  callvirt instance valuetype View System.Web.UI.WebControls.ChangePassword::get_CurrentView()
0x19cbfc  ldc.i4.0
0x19cbfd  ceq
0x19cbff  stloc.2
0x19cc00  ldarg.1
0x19cc01  ldarg.0
0x19cc02  ldstr    aUsernamerequir_0// "UserNameRequired"
0x19cc07  ldloc.1
0x19cc08  ldloc.0
0x19cc09  ldloc.2
0x19cc0a  call     instance class System.Web.UI.WebControls.RequiredFieldValidator DefaultChangePasswordTemplate::CreateRequiredFieldValidator(string id, class System.Web.UI.WebControls.TextBox textBox, string validationGroup, bool enableValidation)
0x19cc0f  callvirt instance void ChangePasswordContainer::set_UserNameRequired(class System.Web.UI.WebControls.RequiredFieldValidator value)
0x19cc14  newobj   instance void System.Web.UI.WebControls.TextBox::.ctor()
0x19cc19  stloc.3
0x19cc1a  ldloc.3
0x19cc1b  ldstr    aCurrentpasswor// "CurrentPassword"
0x19cc20  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19cc25  ldloc.3
0x19cc26  ldc.i4.2
0x19cc27  callvirt instance void System.Web.UI.WebControls.TextBox::set_TextMode(valuetype System.Web.UI.WebControls.TextBoxMode value)
0x19cc2c  ldarg.1
0x19cc2d  ldloc.3
0x19cc2e  callvirt instance void ChangePasswordContainer::set_CurrentPasswordTextBox(class System.Web.UI.Control value)
0x19cc33  ldarg.1
0x19cc34  ldloc.3
0x19cc35  newobj   instance void System.Web.UI.WebControls.LabelLiteral::.ctor(class System.Web.UI.Control forControl)
0x19cc3a  callvirt instance void ChangePasswordContainer::set_CurrentPasswordLabel(class System.Web.UI.WebControls.LabelLiteral value)
0x19cc3f  ldarg.1
0x19cc40  ldarg.0
0x19cc41  ldstr    aCurrentpasswor_0// "CurrentPasswordRequired"
0x19cc46  ldloc.3
0x19cc47  ldloc.0
0x19cc48  ldloc.2
0x19cc49  call     instance class System.Web.UI.WebControls.RequiredFieldValidator DefaultChangePasswordTemplate::CreateRequiredFieldValidator(string id, class System.Web.UI.WebControls.TextBox textBox, string validationGroup, bool enableValidation)
0x19cc4e  callvirt instance void ChangePasswordContainer::set_PasswordRequired(class System.Web.UI.WebControls.RequiredFieldValidator value)
0x19cc53  newobj   instance void System.Web.UI.WebControls.TextBox::.ctor()
0x19cc58  stloc.s  4
0x19cc5a  ldloc.s  4
0x19cc5c  ldstr    aNewpassword_1// "NewPassword"
0x19cc61  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19cc66  ldloc.s  4
0x19cc68  ldc.i4.2
0x19cc69  callvirt instance void System.Web.UI.WebControls.TextBox::set_TextMode(valuetype System.Web.UI.WebControls.TextBoxMode value)
0x19cc6e  ldarg.1
0x19cc6f  ldloc.s  4
0x19cc71  callvirt instance void ChangePasswordContainer::set_NewPasswordTextBox(class System.Web.UI.Control value)
0x19cc76  ldarg.1
0x19cc77  ldloc.s  4
0x19cc79  newobj   instance void System.Web.UI.WebControls.LabelLiteral::.ctor(class System.Web.UI.Control forControl)
0x19cc7e  callvirt instance void ChangePasswordContainer::set_NewPasswordLabel(class System.Web.UI.WebControls.LabelLiteral value)
0x19cc83  ldarg.1
0x19cc84  ldarg.0
0x19cc85  ldstr    aNewpasswordreq_0// "NewPasswordRequired"
0x19cc8a  ldloc.s  4
0x19cc8c  ldloc.0
0x19cc8d  ldloc.2
0x19cc8e  call     instance class System.Web.UI.WebControls.RequiredFieldValidator DefaultChangePasswordTemplate::CreateRequiredFieldValidator(string id, class System.Web.UI.WebControls.TextBox textBox, string validationGroup, bool enableValidation)
0x19cc93  callvirt instance void ChangePasswordContainer::set_NewPasswordRequired(class System.Web.UI.WebControls.RequiredFieldValidator value)
0x19cc98  newobj   instance void System.Web.UI.WebControls.TextBox::.ctor()
0x19cc9d  stloc.s  5
0x19cc9f  ldloc.s  5
0x19cca1  ldstr    aConfirmnewpass_0// "ConfirmNewPassword"
0x19cca6  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19ccab  ldloc.s  5
0x19ccad  ldc.i4.2
0x19ccae  callvirt instance void System.Web.UI.WebControls.TextBox::set_TextMode(valuetype System.Web.UI.WebControls.TextBoxMode value)
0x19ccb3  ldarg.1
0x19ccb4  ldloc.s  5
0x19ccb6  callvirt instance void ChangePasswordContainer::set_ConfirmNewPasswordTextBox(class System.Web.UI.Control value)
0x19ccbb  ldarg.1
0x19ccbc  ldloc.s  5
0x19ccbe  newobj   instance void System.Web.UI.WebControls.LabelLiteral::.ctor(class System.Web.UI.Control forControl)
0x19ccc3  callvirt instance void ChangePasswordContainer::set_ConfirmNewPasswordLabel(class System.Web.UI.WebControls.LabelLiteral value)
0x19ccc8  ldarg.1
0x19ccc9  ldarg.0
0x19ccca  ldstr    aConfirmnewpass_1// "ConfirmNewPasswordRequired"
0x19cccf  ldloc.s  5
0x19ccd1  ldloc.0
0x19ccd2  ldloc.2
0x19ccd3  call     instance class System.Web.UI.WebControls.RequiredFieldValidator DefaultChangePasswordTemplate::CreateRequiredFieldValidator(string id, class System.Web.UI.WebControls.TextBox textBox, string validationGroup, bool enableValidation)
0x19ccd8  callvirt instance void ChangePasswordContainer::set_ConfirmNewPasswordRequired(class System.Web.UI.WebControls.RequiredFieldValidator value)
0x19ccdd  newobj   instance void System.Web.UI.WebControls.CompareValidator::.ctor()
0x19cce2  stloc.s  6
0x19cce4  ldloc.s  6
0x19cce6  ldstr    aNewpasswordcom// "NewPasswordCompare"
0x19cceb  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19ccf0  ldloc.s  6
0x19ccf2  ldloc.0
0x19ccf3  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ValidationGroup(string value)
0x19ccf8  ldloc.s  6
0x19ccfa  ldstr    aConfirmnewpass_0// "ConfirmNewPassword"
0x19ccff  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ControlToValidate(string value)
0x19cd04  ldloc.s  6
0x19cd06  ldstr    aNewpassword_1// "NewPassword"
0x19cd0b  callvirt instance void System.Web.UI.WebControls.CompareValidator::set_ControlToCompare(string value)
0x19cd10  ldloc.s  6
0x19cd12  ldc.i4.0
0x19cd13  callvirt instance void System.Web.UI.WebControls.CompareValidator::set_Operator(valuetype System.Web.UI.WebControls.ValidationCompareOperator value)
0x19cd18  ldloc.s  6
0x19cd1a  ldarg.0
0x19cd1b  ldfld    class System.Web.UI.WebControls.ChangePassword DefaultChangePasswordTemplate::_owner
0x19cd20  callvirt instance string System.Web.UI.WebControls.ChangePassword::get_ConfirmPasswordCompareErrorMessage()
0x19cd25  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ErrorMessage(string value)
0x19cd2a  ldloc.s  6
0x19cd2c  ldc.i4.2
0x19cd2d  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_Display(valuetype System.Web.UI.WebControls.ValidatorDisplay value)
0x19cd32  ldloc.s  6
0x19cd34  ldloc.2
0x19cd35  callvirt instance void System.Web.UI.WebControls.WebControl::set_Enabled(bool value)
0x19cd3a  ldloc.s  6
0x19cd3c  ldloc.2
0x19cd3d  callvirt instance void System.Web.UI.Control::set_Visible(bool value)
0x19cd42  ldarg.1
0x19cd43  ldloc.s  6
0x19cd45  callvirt instance void ChangePasswordContainer::set_NewPasswordCompareValidator(class System.Web.UI.WebControls.CompareValidator value)
0x19cd4a  newobj   instance void System.Web.UI.WebControls.RegularExpressionValidator::.ctor()
0x19cd4f  stloc.s  7
0x19cd51  ldloc.s  7
0x19cd53  ldstr    aNewpasswordreg_1// "NewPasswordRegExp"
0x19cd58  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19cd5d  ldloc.s  7
0x19cd5f  ldloc.0
0x19cd60  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ValidationGroup(string value)
0x19cd65  ldloc.s  7
0x19cd67  ldstr    aNewpassword_1// "NewPassword"
0x19cd6c  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ControlToValidate(string value)
0x19cd71  ldloc.s  7
0x19cd73  ldarg.0
0x19cd74  ldfld    class System.Web.UI.WebControls.ChangePassword DefaultChangePasswordTemplate::_owner
0x19cd79  callvirt instance string System.Web.UI.WebControls.ChangePassword::get_NewPasswordRegularExpressionErrorMessage()
0x19cd7e  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ErrorMessage(string value)
0x19cd83  ldloc.s  7
0x19cd85  ldarg.0
0x19cd86  ldfld    class System.Web.UI.WebControls.ChangePassword DefaultChangePasswordTemplate::_owner
0x19cd8b  callvirt instance string System.Web.UI.WebControls.ChangePassword::get_NewPasswordRegularExpression()
0x19cd90  callvirt instance void System.Web.UI.WebControls.RegularExpressionValidator::set_ValidationExpression(string value)
0x19cd95  ldloc.s  7
0x19cd97  ldc.i4.2
0x19cd98  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_Display(valuetype System.Web.UI.WebControls.ValidatorDisplay value)
0x19cd9d  ldloc.s  7
0x19cd9f  ldloc.2
0x19cda0  callvirt instance void System.Web.UI.WebControls.WebControl::set_Enabled(bool value)
0x19cda5  ldloc.s  7
0x19cda7  ldloc.2
0x19cda8  callvirt instance void System.Web.UI.Control::set_Visible(bool value)
0x19cdad  ldarg.1
0x19cdae  ldloc.s  7
0x19cdb0  callvirt instance void ChangePasswordContainer::set_RegExpValidator(class System.Web.UI.WebControls.RegularExpressionValidator value)
0x19cdb5  newobj   instance void System.Web.UI.WebControls.LinkButton::.ctor()
0x19cdba  stloc.s  8
0x19cdbc  ldloc.s  8
0x19cdbe  ldstr    aChangepassword_22// "ChangePasswordLinkButton"
0x19cdc3  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19cdc8  ldloc.s  8
0x19cdca  ldloc.0
0x19cdcb  callvirt instance void System.Web.UI.WebControls.LinkButton::set_ValidationGroup(string value)
0x19cdd0  ldloc.s  8
0x19cdd2  ldsfld   string System.Web.UI.WebControls.ChangePassword::ChangePasswordButtonCommandName
0x19cdd7  callvirt instance void System.Web.UI.WebControls.LinkButton::set_CommandName(string value)
0x19cddc  ldarg.1
0x19cddd  ldloc.s  8
0x19cddf  callvirt instance void ChangePasswordContainer::set_ChangePasswordLinkButton(class System.Web.UI.WebControls.LinkButton value)
0x19cde4  newobj   instance void System.Web.UI.WebControls.LinkButton::.ctor()
0x19cde9  stloc.s  8
0x19cdeb  ldloc.s  8
0x19cded  ldstr    aCancellinkbutt// "CancelLinkButton"
0x19cdf2  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19cdf7  ldloc.s  8
0x19cdf9  ldc.i4.0
0x19cdfa  callvirt instance void System.Web.UI.WebControls.LinkButton::set_CausesValidation(bool value)
0x19cdff  ldloc.s  8
0x19ce01  ldsfld   string System.Web.UI.WebControls.ChangePassword::CancelButtonCommandName
0x19ce06  callvirt instance void System.Web.UI.WebControls.LinkButton::set_CommandName(string value)
0x19ce0b  ldarg.1
0x19ce0c  ldloc.s  8
0x19ce0e  callvirt instance void ChangePasswordContainer::set_CancelLinkButton(class System.Web.UI.WebControls.LinkButton value)
0x19ce13  newobj   instance void System.Web.UI.WebControls.ImageButton::.ctor()
0x19ce18  stloc.s  9
0x19ce1a  ldloc.s  9
0x19ce1c  ldstr    aChangepassword_23// "ChangePasswordImageButton"
0x19ce21  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19ce26  ldloc.s  9
0x19ce28  ldloc.0
0x19ce29  callvirt instance void System.Web.UI.WebControls.ImageButton::set_ValidationGroup(string value)
0x19ce2e  ldloc.s  9
0x19ce30  ldsfld   string System.Web.UI.WebControls.ChangePassword::ChangePasswordButtonCommandName
0x19ce35  callvirt instance void System.Web.UI.WebControls.ImageButton::set_CommandName(string value)
0x19ce3a  ldarg.1
0x19ce3b  ldloc.s  9
0x19ce3d  callvirt instance void ChangePasswordContainer::set_ChangePasswordImageButton(class System.Web.UI.WebControls.ImageButton value)
0x19ce42  newobj   instance void System.Web.UI.WebControls.ImageButton::.ctor()
0x19ce47  stloc.s  9
0x19ce49  ldloc.s  9
0x19ce4b  ldstr    aCancelimagebut// "CancelImageButton"
0x19ce50  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19ce55  ldloc.s  9
0x19ce57  ldsfld   string System.Web.UI.WebControls.ChangePassword::CancelButtonCommandName
0x19ce5c  callvirt instance void System.Web.UI.WebControls.ImageButton::set_CommandName(string value)
0x19ce61  ldloc.s  9
0x19ce63  ldc.i4.0
0x19ce64  callvirt instance void System.Web.UI.WebControls.ImageButton::set_CausesValidation(bool value)
0x19ce69  ldarg.1
0x19ce6a  ldloc.s  9
0x19ce6c  callvirt instance void ChangePasswordContainer::set_CancelImageButton(class System.Web.UI.WebControls.ImageButton value)
0x19ce71  newobj   instance void System.Web.UI.WebControls.Button::.ctor()
0x19ce76  stloc.s  0xA
0x19ce78  ldloc.s  0xA
0x19ce7a  ldstr    aChangepassword_24// "ChangePasswordPushButton"
0x19ce7f  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19ce84  ldloc.s  0xA
0x19ce86  ldloc.0
0x19ce87  callvirt instance void System.Web.UI.WebControls.Button::set_ValidationGroup(string value)
0x19ce8c  ldloc.s  0xA
0x19ce8e  ldsfld   string System.Web.UI.WebControls.ChangePassword::ChangePasswordButtonCommandName
0x19ce93  callvirt instance void System.Web.UI.WebControls.Button::set_CommandName(string value)
0x19ce98  ldarg.1
0x19ce99  ldloc.s  0xA
0x19ce9b  callvirt instance void ChangePasswordContainer::set_ChangePasswordPushButton(class System.Web.UI.WebControls.Button value)
0x19cea0  newobj   instance void System.Web.UI.WebControls.Button::.ctor()
0x19cea5  stloc.s  0xA
0x19cea7  ldloc.s  0xA
0x19cea9  ldstr    aCancelpushbutt// "CancelPushButton"
0x19ceae  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19ceb3  ldloc.s  0xA
0x19ceb5  ldsfld   string System.Web.UI.WebControls.ChangePassword::CancelButtonCommandName
0x19ceba  callvirt instance void System.Web.UI.WebControls.Button::set_CommandName(string value)
0x19cebf  ldloc.s  0xA
0x19cec1  ldc.i4.0
0x19cec2  callvirt instance void System.Web.UI.WebControls.Button::set_CausesValidation(bool value)
0x19cec7  ldarg.1
0x19cec8  ldloc.s  0xA
0x19ceca  callvirt instance void ChangePasswordContainer::set_CancelPushButton(class System.Web.UI.WebControls.Button value)
0x19cecf  ldarg.1
0x19ced0  newobj   instance void System.Web.UI.WebControls.Image::.ctor()
0x19ced5  callvirt instance void ChangePasswordContainer::set_PasswordRecoveryIcon(class System.Web.UI.WebControls.Image value)
0x19ceda  ldarg.1
0x19cedb  newobj   instance void System.Web.UI.WebControls.HyperLink::.ctor()
0x19cee0  callvirt instance void ChangePasswordContainer::set_PasswordRecoveryLink(class System.Web.UI.WebControls.HyperLink value)
0x19cee5  ldarg.1
0x19cee6  callvirt instance class System.Web.UI.WebControls.HyperLink ChangePasswordContainer::get_PasswordRecoveryLink()
0x19ceeb  ldstr    aPasswordrecove_20// "PasswordRecoveryLink"
0x19cef0  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19cef5  ldarg.1
0x19cef6  newobj   instance void System.Web.UI.WebControls.Image::.ctor()
0x19cefb  callvirt instance void ChangePasswordContainer::set_CreateUserIcon(class System.Web.UI.WebControls.Image value)
0x19cf00  ldarg.1
0x19cf01  newobj   instance void System.Web.UI.WebControls.HyperLink::.ctor()
0x19cf06  callvirt instance void ChangePasswordContainer::set_CreateUserLink(class System.Web.UI.WebControls.HyperLink value)
0x19cf0b  ldarg.1
0x19cf0c  callvirt instance class System.Web.UI.WebControls.HyperLink ChangePasswordContainer::get_CreateUserLink()
0x19cf11  ldstr    aCreateuserlink// "CreateUserLink"
0x19cf16  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19cf1b  ldarg.1
0x19cf1c  newobj   instance void System.Web.UI.LiteralControl::.ctor()
0x19cf21  callvirt instance void ChangePasswordContainer::set_CreateUserLinkSeparator(class System.Web.UI.LiteralControl value)
0x19cf26  ldarg.1
0x19cf27  newobj   instance void System.Web.UI.WebControls.Image::.ctor()
0x19cf2c  callvirt instance void ChangePasswordContainer::set_HelpPageIcon(class System.Web.UI.WebControls.Image value)
0x19cf31  ldarg.1
0x19cf32  newobj   instance void System.Web.UI.WebControls.HyperLink::.ctor()
0x19cf37  callvirt instance void ChangePasswordContainer::set_HelpPageLink(class System.Web.UI.WebControls.HyperLink value)
0x19cf3c  ldarg.1
0x19cf3d  callvirt instance class System.Web.UI.WebControls.HyperLink ChangePasswordContainer::get_HelpPageLink()
0x19cf42  ldstr    aHelplink// "HelpLink"
0x19cf47  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19cf4c  ldarg.1
0x19cf4d  newobj   instance void System.Web.UI.LiteralControl::.ctor()
0x19cf52  callvirt instance void ChangePasswordContainer::set_HelpPageLinkSeparator(class System.Web.UI.LiteralControl value)
0x19cf57  ldarg.1
0x19cf58  newobj   instance void System.Web.UI.WebControls.HyperLink::.ctor()
0x19cf5d  callvirt instance void ChangePasswordContainer::set_EditProfileLink(class System.Web.UI.WebControls.HyperLink value)
0x19cf62  ldarg.1
0x19cf63  callvirt instance class System.Web.UI.WebControls.HyperLink ChangePasswordContainer::get_EditProfileLink()
  ... truncated ...
```
