# DefaultUserNameTemplate::CreateControls

- ea: `0x1a4100`
- end: `0x1a4274`
- name: `DefaultUserNameTemplate::CreateControls`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: ``

## callers

- `0x1a4790`

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
- `0x1a4ac0`
- `0x1a4ae0`
- `0x1a4af0`
- `0x1a4b00`
- `0x1a4b20`
- `0x1a4b40`
- `0x1a4b60`
- `0x1a4b80`
- `0x1a4ba0`
- `0x1a4bc0`
- `0x1a4be0`
- `0x1a4c10`

## string_xrefs

- `0x1a4243`: `HelpLink`
- `0x1a41ae`: `SubmitLinkButton`

## pseudocode

```c

```

## disassembly

```asm
0x1a4100  ldarg.0
0x1a4101  ldfld    class System.Web.UI.WebControls.PasswordRecovery DefaultUserNameTemplate::_owner
0x1a4106  callvirt instance string System.Web.UI.Control::get_UniqueID()
0x1a410b  stloc.0
0x1a410c  ldarg.1
0x1a410d  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x1a4112  callvirt instance void UserNameContainer::set_Title(class System.Web.UI.WebControls.Literal value)
0x1a4117  ldarg.1
0x1a4118  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x1a411d  callvirt instance void UserNameContainer::set_Instruction(class System.Web.UI.WebControls.Literal value)
0x1a4122  newobj   instance void System.Web.UI.WebControls.TextBox::.ctor()
0x1a4127  stloc.1
0x1a4128  ldloc.1
0x1a4129  ldstr    aUsername// "UserName"
0x1a412e  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x1a4133  ldarg.1
0x1a4134  ldloc.1
0x1a4135  callvirt instance void UserNameContainer::set_UserNameTextBox(class System.Web.UI.Control value)
0x1a413a  ldarg.1
0x1a413b  ldloc.1
0x1a413c  newobj   instance void System.Web.UI.WebControls.LabelLiteral::.ctor(class System.Web.UI.Control forControl)
0x1a4141  callvirt instance void UserNameContainer::set_UserNameLabel(class System.Web.UI.WebControls.LabelLiteral value)
0x1a4146  ldarg.0
0x1a4147  ldfld    class System.Web.UI.WebControls.PasswordRecovery DefaultUserNameTemplate::_owner
0x1a414c  callvirt instance valuetype View System.Web.UI.WebControls.PasswordRecovery::get_CurrentView()
0x1a4151  ldc.i4.0
0x1a4152  ceq
0x1a4154  stloc.2
0x1a4155  newobj   instance void System.Web.UI.WebControls.RequiredFieldValidator::.ctor()
0x1a415a  stloc.3
0x1a415b  ldloc.3
0x1a415c  ldstr    aUsernamerequir_0// "UserNameRequired"
0x1a4161  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x1a4166  ldloc.3
0x1a4167  ldloc.0
0x1a4168  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ValidationGroup(string value)
0x1a416d  ldloc.3
0x1a416e  ldloc.1
0x1a416f  callvirt instance string System.Web.UI.Control::get_ID()
0x1a4174  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ControlToValidate(string value)
0x1a4179  ldloc.3
0x1a417a  ldc.i4.1
0x1a417b  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_Display(valuetype System.Web.UI.WebControls.ValidatorDisplay value)
0x1a4180  ldloc.3
0x1a4181  ldstr    aLogincontrolsD_0// "LoginControls_DefaultRequiredFieldValid"...
0x1a4186  call     string System.Web.SR::GetString(string name)
0x1a418b  callvirt instance void System.Web.UI.WebControls.Label::set_Text(string value)
0x1a4190  ldloc.3
0x1a4191  ldloc.2
0x1a4192  callvirt instance void System.Web.UI.WebControls.WebControl::set_Enabled(bool value)
0x1a4197  ldloc.3
0x1a4198  ldloc.2
0x1a4199  callvirt instance void System.Web.UI.Control::set_Visible(bool value)
0x1a419e  ldarg.1
0x1a419f  ldloc.3
0x1a41a0  callvirt instance void UserNameContainer::set_UserNameRequired(class System.Web.UI.WebControls.RequiredFieldValidator value)
0x1a41a5  newobj   instance void System.Web.UI.WebControls.LinkButton::.ctor()
0x1a41aa  stloc.s  4
0x1a41ac  ldloc.s  4
0x1a41ae  ldstr    aSubmitlinkbutt// "SubmitLinkButton"
0x1a41b3  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x1a41b8  ldloc.s  4
0x1a41ba  ldloc.0
0x1a41bb  callvirt instance void System.Web.UI.WebControls.LinkButton::set_ValidationGroup(string value)
0x1a41c0  ldloc.s  4
0x1a41c2  ldsfld   string System.Web.UI.WebControls.PasswordRecovery::SubmitButtonCommandName
0x1a41c7  callvirt instance void System.Web.UI.WebControls.LinkButton::set_CommandName(string value)
0x1a41cc  ldarg.1
0x1a41cd  ldloc.s  4
0x1a41cf  callvirt instance void UserNameContainer::set_LinkButton(class System.Web.UI.WebControls.LinkButton value)
0x1a41d4  newobj   instance void System.Web.UI.WebControls.ImageButton::.ctor()
0x1a41d9  stloc.s  5
0x1a41db  ldloc.s  5
0x1a41dd  ldstr    aSubmitimagebut// "SubmitImageButton"
0x1a41e2  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x1a41e7  ldloc.s  5
0x1a41e9  ldloc.0
0x1a41ea  callvirt instance void System.Web.UI.WebControls.ImageButton::set_ValidationGroup(string value)
0x1a41ef  ldloc.s  5
0x1a41f1  ldsfld   string System.Web.UI.WebControls.PasswordRecovery::SubmitButtonCommandName
0x1a41f6  callvirt instance void System.Web.UI.WebControls.ImageButton::set_CommandName(string value)
0x1a41fb  ldarg.1
0x1a41fc  ldloc.s  5
0x1a41fe  callvirt instance void UserNameContainer::set_ImageButton(class System.Web.UI.WebControls.ImageButton value)
0x1a4203  newobj   instance void System.Web.UI.WebControls.Button::.ctor()
0x1a4208  stloc.s  6
0x1a420a  ldloc.s  6
0x1a420c  ldstr    aSubmitbutton// "SubmitButton"
0x1a4211  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x1a4216  ldloc.s  6
0x1a4218  ldloc.0
0x1a4219  callvirt instance void System.Web.UI.WebControls.Button::set_ValidationGroup(string value)
0x1a421e  ldloc.s  6
0x1a4220  ldsfld   string System.Web.UI.WebControls.PasswordRecovery::SubmitButtonCommandName
0x1a4225  callvirt instance void System.Web.UI.WebControls.Button::set_CommandName(string value)
0x1a422a  ldarg.1
0x1a422b  ldloc.s  6
0x1a422d  callvirt instance void UserNameContainer::set_PushButton(class System.Web.UI.WebControls.Button value)
0x1a4232  ldarg.1
0x1a4233  newobj   instance void System.Web.UI.WebControls.HyperLink::.ctor()
0x1a4238  callvirt instance void UserNameContainer::set_HelpPageLink(class System.Web.UI.WebControls.HyperLink value)
0x1a423d  ldarg.1
0x1a423e  callvirt instance class System.Web.UI.WebControls.HyperLink UserNameContainer::get_HelpPageLink()
0x1a4243  ldstr    aHelplink// "HelpLink"
0x1a4248  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x1a424d  ldarg.1
0x1a424e  newobj   instance void System.Web.UI.WebControls.Image::.ctor()
0x1a4253  callvirt instance void UserNameContainer::set_HelpPageIcon(class System.Web.UI.WebControls.Image value)
0x1a4258  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x1a425d  stloc.s  7
0x1a425f  ldloc.s  7
0x1a4261  ldstr    aFailuretext// "FailureText"
0x1a4266  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x1a426b  ldarg.1
0x1a426c  ldloc.s  7
0x1a426e  callvirt instance void UserNameContainer::set_FailureTextLabel(class System.Web.UI.Control value)
0x1a4273  ret
```
