# DefaultCreateUserContentTemplate::ConstructControls

- ea: `0x19dee0`
- end: `0x19e1f5`
- name: `DefaultCreateUserContentTemplate::ConstructControls`
- size: `789`
- prototype: ``
- caller_count: `1`
- callee_count: `60`
- tags: `broker_com_uri`

## callers

- `0x19e6c0`

## callees

- `0x5f1e0`
- `0x5fc20`
- `0x60050`
- `0x916b0`
- `0x91700`
- `0x91820`
- `0x918e0`
- `0x9c720`
- `0x9c760`
- `0x9ca60`
- `0x9db50`
- `0x9e230`
- `0x9e280`
- `0x9e8b0`
- `0x9e900`
- `0x9ed60`
- `0xa0010`
- `0xa0020`
- `0xa0030`
- `0xb9930`
- `0xbaf70`
- `0xbf6d0`
- `0xd5450`
- `0xd5580`
- `0xdf2c0`
- `0xdf460`
- `0xea6f0`
- `0x19eb60`
- `0x19eb80`
- `0x19eb90`
- `0x19ec00`
- `0x19ec20`
- `0x19ec40`
- `0x19ec50`
- `0x19ec80`
- `0x19eca0`
- `0x19ecc0`
- `0x19ece0`
- `0x19ecf0`
- `0x19ed60`
- `0x19ed80`
- `0x19edc0`
- `0x19ede0`
- `0x19ee00`
- `0x19ee20`
- `0x19ee40`
- `0x19ee60`
- `0x19ee80`
- `0x19eea0`
- `0x19eeb0`

## string_xrefs

- `0x19dfc4`: `HelpLink`
- `0x19e11d`: `PasswordCompare`

## pseudocode

```c

```

## disassembly

```asm
0x19dee0  ldarg.0
0x19dee1  ldfld    class System.Web.UI.WebControls.CreateUserWizard DefaultCreateUserContentTemplate::_wizard
0x19dee6  callvirt instance string System.Web.UI.WebControls.CreateUserWizard::get_ValidationGroup()
0x19deeb  stloc.0
0x19deec  ldarg.1
0x19deed  call     class System.Web.UI.WebControls.Literal System.Web.UI.WebControls.CreateUserWizard::CreateLiteral()
0x19def2  callvirt instance void CreateUserStepContainer::set_Title(class System.Web.UI.WebControls.Literal value)
0x19def7  ldarg.1
0x19def8  call     class System.Web.UI.WebControls.Literal System.Web.UI.WebControls.CreateUserWizard::CreateLiteral()
0x19defd  callvirt instance void CreateUserStepContainer::set_InstructionLabel(class System.Web.UI.WebControls.Literal value)
0x19df02  ldarg.1
0x19df03  call     class System.Web.UI.WebControls.Literal System.Web.UI.WebControls.CreateUserWizard::CreateLiteral()
0x19df08  callvirt instance void CreateUserStepContainer::set_PasswordHintLabel(class System.Web.UI.WebControls.Literal value)
0x19df0d  ldarg.1
0x19df0e  newobj   instance void System.Web.UI.WebControls.TextBox::.ctor()
0x19df13  dup
0x19df14  ldstr    aUsername// "UserName"
0x19df19  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19df1e  callvirt instance void CreateUserStepContainer::set_UserNameTextBox(class System.Web.UI.Control value)
0x19df23  ldarg.1
0x19df24  newobj   instance void System.Web.UI.WebControls.TextBox::.ctor()
0x19df29  dup
0x19df2a  ldstr    aPassword_1// "Password"
0x19df2f  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19df34  dup
0x19df35  ldc.i4.2
0x19df36  callvirt instance void System.Web.UI.WebControls.TextBox::set_TextMode(valuetype System.Web.UI.WebControls.TextBoxMode value)
0x19df3b  callvirt instance void CreateUserStepContainer::set_PasswordTextBox(class System.Web.UI.Control value)
0x19df40  ldarg.1
0x19df41  newobj   instance void System.Web.UI.WebControls.TextBox::.ctor()
0x19df46  dup
0x19df47  ldstr    aConfirmpasswor_2// "ConfirmPassword"
0x19df4c  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19df51  dup
0x19df52  ldc.i4.2
0x19df53  callvirt instance void System.Web.UI.WebControls.TextBox::set_TextMode(valuetype System.Web.UI.WebControls.TextBoxMode value)
0x19df58  callvirt instance void CreateUserStepContainer::set_ConfirmPasswordTextBox(class System.Web.UI.Control value)
0x19df5d  ldc.i4.1
0x19df5e  stloc.1
0x19df5f  ldarg.1
0x19df60  ldstr    aUsernamerequir_0// "UserNameRequired"
0x19df65  ldloc.0
0x19df66  ldarg.1
0x19df67  callvirt instance class System.Web.UI.Control CreateUserStepContainer::get_UserNameTextBox()
0x19df6c  ldloc.1
0x19df6d  call     class System.Web.UI.WebControls.RequiredFieldValidator System.Web.UI.WebControls.CreateUserWizard::CreateRequiredFieldValidator(string id, string validationGroup, class System.Web.UI.Control targetTextBox, bool enableValidation)
0x19df72  callvirt instance void CreateUserStepContainer::set_UserNameRequired(class System.Web.UI.WebControls.RequiredFieldValidator value)
0x19df77  ldarg.1
0x19df78  ldarg.1
0x19df79  callvirt instance class System.Web.UI.Control CreateUserStepContainer::get_UserNameTextBox()
0x19df7e  call     class System.Web.UI.WebControls.LabelLiteral System.Web.UI.WebControls.CreateUserWizard::CreateLabelLiteral(class System.Web.UI.Control control)
0x19df83  callvirt instance void CreateUserStepContainer::set_UserNameLabel(class System.Web.UI.WebControls.LabelLiteral value)
0x19df88  ldarg.1
0x19df89  ldarg.1
0x19df8a  callvirt instance class System.Web.UI.Control CreateUserStepContainer::get_PasswordTextBox()
0x19df8f  call     class System.Web.UI.WebControls.LabelLiteral System.Web.UI.WebControls.CreateUserWizard::CreateLabelLiteral(class System.Web.UI.Control control)
0x19df94  callvirt instance void CreateUserStepContainer::set_PasswordLabel(class System.Web.UI.WebControls.LabelLiteral value)
0x19df99  ldarg.1
0x19df9a  ldarg.1
0x19df9b  callvirt instance class System.Web.UI.Control CreateUserStepContainer::get_ConfirmPasswordTextBox()
0x19dfa0  call     class System.Web.UI.WebControls.LabelLiteral System.Web.UI.WebControls.CreateUserWizard::CreateLabelLiteral(class System.Web.UI.Control control)
0x19dfa5  callvirt instance void CreateUserStepContainer::set_ConfirmPasswordLabel(class System.Web.UI.WebControls.LabelLiteral value)
0x19dfaa  newobj   instance void System.Web.UI.WebControls.Image::.ctor()
0x19dfaf  stloc.2
0x19dfb0  ldloc.2
0x19dfb1  callvirt instance void System.Web.UI.Control::PreventAutoID()
0x19dfb6  ldarg.1
0x19dfb7  ldloc.2
0x19dfb8  callvirt instance void CreateUserStepContainer::set_HelpPageIcon(class System.Web.UI.WebControls.Image value)
0x19dfbd  ldarg.1
0x19dfbe  newobj   instance void System.Web.UI.WebControls.HyperLink::.ctor()
0x19dfc3  dup
0x19dfc4  ldstr    aHelplink// "HelpLink"
0x19dfc9  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19dfce  callvirt instance void CreateUserStepContainer::set_HelpPageLink(class System.Web.UI.WebControls.HyperLink value)
0x19dfd3  ldarg.1
0x19dfd4  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x19dfd9  dup
0x19dfda  ldstr    aErrormessage// "ErrorMessage"
0x19dfdf  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19dfe4  callvirt instance void CreateUserStepContainer::set_ErrorMessageLabel(class System.Web.UI.Control value)
0x19dfe9  ldarg.1
0x19dfea  newobj   instance void System.Web.UI.WebControls.TextBox::.ctor()
0x19dfef  dup
0x19dff0  ldstr    aEmail// "Email"
0x19dff5  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19dffa  callvirt instance void CreateUserStepContainer::set_EmailTextBox(class System.Web.UI.Control value)
0x19dfff  ldarg.1
0x19e000  ldstr    aEmailrequired// "EmailRequired"
0x19e005  ldloc.0
0x19e006  ldarg.1
0x19e007  callvirt instance class System.Web.UI.Control CreateUserStepContainer::get_EmailTextBox()
0x19e00c  ldloc.1
0x19e00d  call     class System.Web.UI.WebControls.RequiredFieldValidator System.Web.UI.WebControls.CreateUserWizard::CreateRequiredFieldValidator(string id, string validationGroup, class System.Web.UI.Control targetTextBox, bool enableValidation)
0x19e012  callvirt instance void CreateUserStepContainer::set_EmailRequired(class System.Web.UI.WebControls.RequiredFieldValidator value)
0x19e017  ldarg.1
0x19e018  ldarg.1
0x19e019  callvirt instance class System.Web.UI.Control CreateUserStepContainer::get_EmailTextBox()
0x19e01e  call     class System.Web.UI.WebControls.LabelLiteral System.Web.UI.WebControls.CreateUserWizard::CreateLabelLiteral(class System.Web.UI.Control control)
0x19e023  callvirt instance void CreateUserStepContainer::set_EmailLabel(class System.Web.UI.WebControls.LabelLiteral value)
0x19e028  ldarg.1
0x19e029  newobj   instance void System.Web.UI.WebControls.RegularExpressionValidator::.ctor()
0x19e02e  dup
0x19e02f  ldstr    aEmailregexp// "EmailRegExp"
0x19e034  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19e039  dup
0x19e03a  ldstr    aEmail// "Email"
0x19e03f  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ControlToValidate(string value)
0x19e044  dup
0x19e045  ldarg.0
0x19e046  ldfld    class System.Web.UI.WebControls.CreateUserWizard DefaultCreateUserContentTemplate::_wizard
0x19e04b  callvirt instance string System.Web.UI.WebControls.CreateUserWizard::get_EmailRegularExpressionErrorMessage()
0x19e050  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ErrorMessage(string value)
0x19e055  dup
0x19e056  ldarg.0
0x19e057  ldfld    class System.Web.UI.WebControls.CreateUserWizard DefaultCreateUserContentTemplate::_wizard
0x19e05c  callvirt instance string System.Web.UI.WebControls.CreateUserWizard::get_EmailRegularExpression()
0x19e061  callvirt instance void System.Web.UI.WebControls.RegularExpressionValidator::set_ValidationExpression(string value)
0x19e066  dup
0x19e067  ldloc.0
0x19e068  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ValidationGroup(string value)
0x19e06d  dup
0x19e06e  ldc.i4.2
0x19e06f  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_Display(valuetype System.Web.UI.WebControls.ValidatorDisplay value)
0x19e074  dup
0x19e075  ldloc.1
0x19e076  callvirt instance void System.Web.UI.WebControls.WebControl::set_Enabled(bool value)
0x19e07b  dup
0x19e07c  ldloc.1
0x19e07d  callvirt instance void System.Web.UI.Control::set_Visible(bool value)
0x19e082  callvirt instance void CreateUserStepContainer::set_EmailRegExpValidator(class System.Web.UI.WebControls.RegularExpressionValidator value)
0x19e087  ldarg.1
0x19e088  ldstr    aPasswordrequir_0// "PasswordRequired"
0x19e08d  ldloc.0
0x19e08e  ldarg.1
0x19e08f  callvirt instance class System.Web.UI.Control CreateUserStepContainer::get_PasswordTextBox()
0x19e094  ldloc.1
0x19e095  call     class System.Web.UI.WebControls.RequiredFieldValidator System.Web.UI.WebControls.CreateUserWizard::CreateRequiredFieldValidator(string id, string validationGroup, class System.Web.UI.Control targetTextBox, bool enableValidation)
0x19e09a  callvirt instance void CreateUserStepContainer::set_PasswordRequired(class System.Web.UI.WebControls.RequiredFieldValidator value)
0x19e09f  ldarg.1
0x19e0a0  ldstr    aConfirmpasswor_3// "ConfirmPasswordRequired"
0x19e0a5  ldloc.0
0x19e0a6  ldarg.1
0x19e0a7  callvirt instance class System.Web.UI.Control CreateUserStepContainer::get_ConfirmPasswordTextBox()
0x19e0ac  ldloc.1
0x19e0ad  call     class System.Web.UI.WebControls.RequiredFieldValidator System.Web.UI.WebControls.CreateUserWizard::CreateRequiredFieldValidator(string id, string validationGroup, class System.Web.UI.Control targetTextBox, bool enableValidation)
0x19e0b2  callvirt instance void CreateUserStepContainer::set_ConfirmPasswordRequired(class System.Web.UI.WebControls.RequiredFieldValidator value)
0x19e0b7  ldarg.1
0x19e0b8  newobj   instance void System.Web.UI.WebControls.RegularExpressionValidator::.ctor()
0x19e0bd  dup
0x19e0be  ldstr    aPasswordregexp// "PasswordRegExp"
0x19e0c3  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19e0c8  dup
0x19e0c9  ldstr    aPassword_1// "Password"
0x19e0ce  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ControlToValidate(string value)
0x19e0d3  dup
0x19e0d4  ldarg.0
0x19e0d5  ldfld    class System.Web.UI.WebControls.CreateUserWizard DefaultCreateUserContentTemplate::_wizard
0x19e0da  callvirt instance string System.Web.UI.WebControls.CreateUserWizard::get_PasswordRegularExpressionErrorMessage()
0x19e0df  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ErrorMessage(string value)
0x19e0e4  dup
0x19e0e5  ldarg.0
0x19e0e6  ldfld    class System.Web.UI.WebControls.CreateUserWizard DefaultCreateUserContentTemplate::_wizard
0x19e0eb  callvirt instance string System.Web.UI.WebControls.CreateUserWizard::get_PasswordRegularExpression()
0x19e0f0  callvirt instance void System.Web.UI.WebControls.RegularExpressionValidator::set_ValidationExpression(string value)
0x19e0f5  dup
0x19e0f6  ldloc.0
0x19e0f7  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ValidationGroup(string value)
0x19e0fc  dup
0x19e0fd  ldc.i4.2
0x19e0fe  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_Display(valuetype System.Web.UI.WebControls.ValidatorDisplay value)
0x19e103  dup
0x19e104  ldloc.1
0x19e105  callvirt instance void System.Web.UI.WebControls.WebControl::set_Enabled(bool value)
0x19e10a  dup
0x19e10b  ldloc.1
0x19e10c  callvirt instance void System.Web.UI.Control::set_Visible(bool value)
0x19e111  callvirt instance void CreateUserStepContainer::set_PasswordRegExpValidator(class System.Web.UI.WebControls.RegularExpressionValidator value)
0x19e116  ldarg.1
0x19e117  newobj   instance void System.Web.UI.WebControls.CompareValidator::.ctor()
0x19e11c  dup
0x19e11d  ldstr    aPasswordcompar// "PasswordCompare"
0x19e122  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19e127  dup
0x19e128  ldstr    aConfirmpasswor_2// "ConfirmPassword"
0x19e12d  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ControlToValidate(string value)
0x19e132  dup
0x19e133  ldstr    aPassword_1// "Password"
0x19e138  callvirt instance void System.Web.UI.WebControls.CompareValidator::set_ControlToCompare(string value)
0x19e13d  dup
0x19e13e  ldc.i4.0
0x19e13f  callvirt instance void System.Web.UI.WebControls.CompareValidator::set_Operator(valuetype System.Web.UI.WebControls.ValidationCompareOperator value)
0x19e144  dup
0x19e145  ldarg.0
0x19e146  ldfld    class System.Web.UI.WebControls.CreateUserWizard DefaultCreateUserContentTemplate::_wizard
0x19e14b  callvirt instance string System.Web.UI.WebControls.CreateUserWizard::get_ConfirmPasswordCompareErrorMessage()
0x19e150  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ErrorMessage(string value)
0x19e155  dup
0x19e156  ldloc.0
0x19e157  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ValidationGroup(string value)
0x19e15c  dup
0x19e15d  ldc.i4.2
0x19e15e  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_Display(valuetype System.Web.UI.WebControls.ValidatorDisplay value)
0x19e163  dup
0x19e164  ldloc.1
0x19e165  callvirt instance void System.Web.UI.WebControls.WebControl::set_Enabled(bool value)
0x19e16a  dup
0x19e16b  ldloc.1
0x19e16c  callvirt instance void System.Web.UI.Control::set_Visible(bool value)
0x19e171  callvirt instance void CreateUserStepContainer::set_PasswordCompareValidator(class System.Web.UI.WebControls.CompareValidator value)
0x19e176  ldarg.1
0x19e177  newobj   instance void System.Web.UI.WebControls.TextBox::.ctor()
0x19e17c  dup
0x19e17d  ldstr    aQuestion// "Question"
0x19e182  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19e187  callvirt instance void CreateUserStepContainer::set_QuestionTextBox(class System.Web.UI.Control value)
0x19e18c  ldarg.1
0x19e18d  newobj   instance void System.Web.UI.WebControls.TextBox::.ctor()
0x19e192  dup
0x19e193  ldstr    aAnswer// "Answer"
0x19e198  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19e19d  callvirt instance void CreateUserStepContainer::set_AnswerTextBox(class System.Web.UI.Control value)
0x19e1a2  ldarg.1
0x19e1a3  ldstr    aQuestionrequir_0// "QuestionRequired"
0x19e1a8  ldloc.0
0x19e1a9  ldarg.1
0x19e1aa  callvirt instance class System.Web.UI.Control CreateUserStepContainer::get_QuestionTextBox()
0x19e1af  ldloc.1
0x19e1b0  call     class System.Web.UI.WebControls.RequiredFieldValidator System.Web.UI.WebControls.CreateUserWizard::CreateRequiredFieldValidator(string id, string validationGroup, class System.Web.UI.Control targetTextBox, bool enableValidation)
0x19e1b5  callvirt instance void CreateUserStepContainer::set_QuestionRequired(class System.Web.UI.WebControls.RequiredFieldValidator value)
0x19e1ba  ldarg.1
0x19e1bb  ldstr    aAnswerrequired_0// "AnswerRequired"
0x19e1c0  ldloc.0
0x19e1c1  ldarg.1
0x19e1c2  callvirt instance class System.Web.UI.Control CreateUserStepContainer::get_AnswerTextBox()
0x19e1c7  ldloc.1
0x19e1c8  call     class System.Web.UI.WebControls.RequiredFieldValidator System.Web.UI.WebControls.CreateUserWizard::CreateRequiredFieldValidator(string id, string validationGroup, class System.Web.UI.Control targetTextBox, bool enableValidation)
0x19e1cd  callvirt instance void CreateUserStepContainer::set_AnswerRequired(class System.Web.UI.WebControls.RequiredFieldValidator value)
0x19e1d2  ldarg.1
0x19e1d3  ldarg.1
0x19e1d4  callvirt instance class System.Web.UI.Control CreateUserStepContainer::get_QuestionTextBox()
0x19e1d9  call     class System.Web.UI.WebControls.LabelLiteral System.Web.UI.WebControls.CreateUserWizard::CreateLabelLiteral(class System.Web.UI.Control control)
0x19e1de  callvirt instance void CreateUserStepContainer::set_QuestionLabel(class System.Web.UI.WebControls.LabelLiteral value)
0x19e1e3  ldarg.1
0x19e1e4  ldarg.1
0x19e1e5  callvirt instance class System.Web.UI.Control CreateUserStepContainer::get_AnswerTextBox()
0x19e1ea  call     class System.Web.UI.WebControls.LabelLiteral System.Web.UI.WebControls.CreateUserWizard::CreateLabelLiteral(class System.Web.UI.Control control)
0x19e1ef  callvirt instance void CreateUserStepContainer::set_AnswerLabel(class System.Web.UI.WebControls.LabelLiteral value)
0x19e1f4  ret
```
