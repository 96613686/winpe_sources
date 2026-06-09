# LoginTemplate::CreateControls

- ea: `0x19f300`
- end: `0x19f590`
- name: `LoginTemplate::CreateControls`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `49`
- tags: ``

## callers

- `0x1a0470`

## callees

- `0x34fa0`
- `0x5f1b0`
- `0x5f1e0`
- `0x5fc20`
- `0x5fc90`
- `0x6e540`
- `0x916b0`
- `0x91820`
- `0x918e0`
- `0x936b0`
- `0x93730`
- `0x93900`
- `0x99810`
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
- `0xd70e0`
- `0xdf2c0`
- `0xdf460`
- `0xea6f0`
- `0x1a04f0`
- `0x1a0510`
- `0x1a0530`
- `0x1a0550`
- `0x1a0570`
- `0x1a05a0`
- `0x1a05c0`
- `0x1a05e0`
- `0x1a0600`
- `0x1a0620`
- `0x1a0640`
- `0x1a0660`
- `0x1a0680`
- `0x1a06a0`
- `0x1a06d0`
- `0x1a06f0`
- `0x1a0720`
- `0x1a0740`
- `0x1a0760`
- `0x1a0780`
- `0x1a07b0`

## string_xrefs

- `0x19f4fc`: `PasswordRecoveryLink`
- `0x19f51f`: `CreateUserLink`
- `0x19f541`: `HelpLink`
- `0x19f460`: `LoginLinkButton`

## pseudocode

```c

```

## disassembly

```asm
0x19f300  ldarg.0
0x19f301  ldfld    class System.Web.UI.WebControls.Login LoginTemplate::_owner
0x19f306  callvirt instance string System.Web.UI.Control::get_UniqueID()
0x19f30b  stloc.0
0x19f30c  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x19f311  stloc.1
0x19f312  ldarg.1
0x19f313  ldloc.1
0x19f314  callvirt instance void LoginContainer::set_Title(class System.Web.UI.WebControls.Literal value)
0x19f319  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x19f31e  stloc.2
0x19f31f  ldarg.1
0x19f320  ldloc.2
0x19f321  callvirt instance void LoginContainer::set_Instruction(class System.Web.UI.WebControls.Literal value)
0x19f326  newobj   instance void System.Web.UI.WebControls.TextBox::.ctor()
0x19f32b  stloc.3
0x19f32c  ldloc.3
0x19f32d  ldstr    aUsername// "UserName"
0x19f332  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19f337  ldarg.1
0x19f338  ldloc.3
0x19f339  callvirt instance void LoginContainer::set_UserNameTextBox(class System.Web.UI.Control value)
0x19f33e  ldloc.3
0x19f33f  newobj   instance void System.Web.UI.WebControls.LabelLiteral::.ctor(class System.Web.UI.Control forControl)
0x19f344  stloc.s  4
0x19f346  ldarg.1
0x19f347  ldloc.s  4
0x19f349  callvirt instance void LoginContainer::set_UserNameLabel(class System.Web.UI.WebControls.LabelLiteral value)
0x19f34e  ldc.i4.1
0x19f34f  stloc.s  5
0x19f351  newobj   instance void System.Web.UI.WebControls.RequiredFieldValidator::.ctor()
0x19f356  stloc.s  6
0x19f358  ldloc.s  6
0x19f35a  ldstr    aUsernamerequir_0// "UserNameRequired"
0x19f35f  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19f364  ldloc.s  6
0x19f366  ldloc.0
0x19f367  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ValidationGroup(string value)
0x19f36c  ldloc.s  6
0x19f36e  ldloc.3
0x19f36f  callvirt instance string System.Web.UI.Control::get_ID()
0x19f374  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ControlToValidate(string value)
0x19f379  ldloc.s  6
0x19f37b  ldc.i4.1
0x19f37c  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_Display(valuetype System.Web.UI.WebControls.ValidatorDisplay value)
0x19f381  ldloc.s  6
0x19f383  ldstr    aLogincontrolsD_0// "LoginControls_DefaultRequiredFieldValid"...
0x19f388  call     string System.Web.SR::GetString(string name)
0x19f38d  callvirt instance void System.Web.UI.WebControls.Label::set_Text(string value)
0x19f392  ldloc.s  6
0x19f394  ldloc.s  5
0x19f396  callvirt instance void System.Web.UI.WebControls.WebControl::set_Enabled(bool value)
0x19f39b  ldloc.s  6
0x19f39d  ldloc.s  5
0x19f39f  callvirt instance void System.Web.UI.Control::set_Visible(bool value)
0x19f3a4  ldarg.1
0x19f3a5  ldloc.s  6
0x19f3a7  callvirt instance void LoginContainer::set_UserNameRequired(class System.Web.UI.WebControls.RequiredFieldValidator value)
0x19f3ac  newobj   instance void System.Web.UI.WebControls.TextBox::.ctor()
0x19f3b1  stloc.s  7
0x19f3b3  ldloc.s  7
0x19f3b5  ldstr    aPassword_1// "Password"
0x19f3ba  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19f3bf  ldloc.s  7
0x19f3c1  ldc.i4.2
0x19f3c2  callvirt instance void System.Web.UI.WebControls.TextBox::set_TextMode(valuetype System.Web.UI.WebControls.TextBoxMode value)
0x19f3c7  ldarg.1
0x19f3c8  ldloc.s  7
0x19f3ca  callvirt instance void LoginContainer::set_PasswordTextBox(class System.Web.UI.Control value)
0x19f3cf  ldloc.s  7
0x19f3d1  newobj   instance void System.Web.UI.WebControls.LabelLiteral::.ctor(class System.Web.UI.Control forControl)
0x19f3d6  stloc.s  8
0x19f3d8  ldarg.1
0x19f3d9  ldloc.s  8
0x19f3db  callvirt instance void LoginContainer::set_PasswordLabel(class System.Web.UI.WebControls.LabelLiteral value)
0x19f3e0  newobj   instance void System.Web.UI.WebControls.RequiredFieldValidator::.ctor()
0x19f3e5  stloc.s  9
0x19f3e7  ldloc.s  9
0x19f3e9  ldstr    aPasswordrequir_0// "PasswordRequired"
0x19f3ee  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19f3f3  ldloc.s  9
0x19f3f5  ldloc.0
0x19f3f6  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ValidationGroup(string value)
0x19f3fb  ldloc.s  9
0x19f3fd  ldloc.s  7
0x19f3ff  callvirt instance string System.Web.UI.Control::get_ID()
0x19f404  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_ControlToValidate(string value)
0x19f409  ldloc.s  9
0x19f40b  ldc.i4.1
0x19f40c  callvirt instance void System.Web.UI.WebControls.BaseValidator::set_Display(valuetype System.Web.UI.WebControls.ValidatorDisplay value)
0x19f411  ldloc.s  9
0x19f413  ldstr    aLogincontrolsD_0// "LoginControls_DefaultRequiredFieldValid"...
0x19f418  call     string System.Web.SR::GetString(string name)
0x19f41d  callvirt instance void System.Web.UI.WebControls.Label::set_Text(string value)
0x19f422  ldloc.s  9
0x19f424  ldloc.s  5
0x19f426  callvirt instance void System.Web.UI.WebControls.WebControl::set_Enabled(bool value)
0x19f42b  ldloc.s  9
0x19f42d  ldloc.s  5
0x19f42f  callvirt instance void System.Web.UI.Control::set_Visible(bool value)
0x19f434  ldarg.1
0x19f435  ldloc.s  9
0x19f437  callvirt instance void LoginContainer::set_PasswordRequired(class System.Web.UI.WebControls.RequiredFieldValidator value)
0x19f43c  newobj   instance void System.Web.UI.WebControls.CheckBox::.ctor()
0x19f441  stloc.s  0xA
0x19f443  ldloc.s  0xA
0x19f445  ldstr    aRememberme// "RememberMe"
0x19f44a  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19f44f  ldarg.1
0x19f450  ldloc.s  0xA
0x19f452  callvirt instance void LoginContainer::set_RememberMeCheckBox(class System.Web.UI.Control value)
0x19f457  newobj   instance void System.Web.UI.WebControls.LinkButton::.ctor()
0x19f45c  stloc.s  0xB
0x19f45e  ldloc.s  0xB
0x19f460  ldstr    aLoginlinkbutto// "LoginLinkButton"
0x19f465  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19f46a  ldloc.s  0xB
0x19f46c  ldloc.0
0x19f46d  callvirt instance void System.Web.UI.WebControls.LinkButton::set_ValidationGroup(string value)
0x19f472  ldloc.s  0xB
0x19f474  ldsfld   string System.Web.UI.WebControls.Login::LoginButtonCommandName
0x19f479  callvirt instance void System.Web.UI.WebControls.LinkButton::set_CommandName(string value)
0x19f47e  ldarg.1
0x19f47f  ldloc.s  0xB
0x19f481  callvirt instance void LoginContainer::set_LinkButton(class System.Web.UI.WebControls.LinkButton value)
0x19f486  newobj   instance void System.Web.UI.WebControls.ImageButton::.ctor()
0x19f48b  stloc.s  0xC
0x19f48d  ldloc.s  0xC
0x19f48f  ldstr    aLoginimagebutt// "LoginImageButton"
0x19f494  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19f499  ldloc.s  0xC
0x19f49b  ldloc.0
0x19f49c  callvirt instance void System.Web.UI.WebControls.ImageButton::set_ValidationGroup(string value)
0x19f4a1  ldloc.s  0xC
0x19f4a3  ldsfld   string System.Web.UI.WebControls.Login::LoginButtonCommandName
0x19f4a8  callvirt instance void System.Web.UI.WebControls.ImageButton::set_CommandName(string value)
0x19f4ad  ldarg.1
0x19f4ae  ldloc.s  0xC
0x19f4b0  callvirt instance void LoginContainer::set_ImageButton(class System.Web.UI.WebControls.ImageButton value)
0x19f4b5  newobj   instance void System.Web.UI.WebControls.Button::.ctor()
0x19f4ba  stloc.s  0xD
0x19f4bc  ldloc.s  0xD
0x19f4be  ldstr    aLoginbutton// "LoginButton"
0x19f4c3  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19f4c8  ldloc.s  0xD
0x19f4ca  ldloc.0
0x19f4cb  callvirt instance void System.Web.UI.WebControls.Button::set_ValidationGroup(string value)
0x19f4d0  ldloc.s  0xD
0x19f4d2  ldsfld   string System.Web.UI.WebControls.Login::LoginButtonCommandName
0x19f4d7  callvirt instance void System.Web.UI.WebControls.Button::set_CommandName(string value)
0x19f4dc  ldarg.1
0x19f4dd  ldloc.s  0xD
0x19f4df  callvirt instance void LoginContainer::set_PushButton(class System.Web.UI.WebControls.Button value)
0x19f4e4  newobj   instance void System.Web.UI.WebControls.HyperLink::.ctor()
0x19f4e9  stloc.s  0xE
0x19f4eb  ldarg.1
0x19f4ec  ldloc.s  0xE
0x19f4ee  callvirt instance void LoginContainer::set_PasswordRecoveryLink(class System.Web.UI.WebControls.HyperLink value)
0x19f4f3  newobj   instance void System.Web.UI.LiteralControl::.ctor()
0x19f4f8  stloc.s  0xF
0x19f4fa  ldloc.s  0xE
0x19f4fc  ldstr    aPasswordrecove_20// "PasswordRecoveryLink"
0x19f501  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19f506  ldarg.1
0x19f507  ldloc.s  0xF
0x19f509  callvirt instance void LoginContainer::set_PasswordRecoveryLinkSeparator(class System.Web.UI.LiteralControl value)
0x19f50e  newobj   instance void System.Web.UI.WebControls.HyperLink::.ctor()
0x19f513  stloc.s  0x10
0x19f515  ldarg.1
0x19f516  ldloc.s  0x10
0x19f518  callvirt instance void LoginContainer::set_CreateUserLink(class System.Web.UI.WebControls.HyperLink value)
0x19f51d  ldloc.s  0x10
0x19f51f  ldstr    aCreateuserlink// "CreateUserLink"
0x19f524  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19f529  newobj   instance void System.Web.UI.LiteralControl::.ctor()
0x19f52e  stloc.s  0x11
0x19f530  ldarg.1
0x19f531  ldloc.s  0x11
0x19f533  callvirt instance void LoginContainer::set_CreateUserLinkSeparator(class System.Web.UI.LiteralControl value)
0x19f538  newobj   instance void System.Web.UI.WebControls.HyperLink::.ctor()
0x19f53d  stloc.s  0x12
0x19f53f  ldloc.s  0x12
0x19f541  ldstr    aHelplink// "HelpLink"
0x19f546  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19f54b  ldarg.1
0x19f54c  ldloc.s  0x12
0x19f54e  callvirt instance void LoginContainer::set_HelpPageLink(class System.Web.UI.WebControls.HyperLink value)
0x19f553  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x19f558  stloc.s  0x13
0x19f55a  ldloc.s  0x13
0x19f55c  ldstr    aFailuretext// "FailureText"
0x19f561  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19f566  ldarg.1
0x19f567  ldloc.s  0x13
0x19f569  callvirt instance void LoginContainer::set_FailureTextLabel(class System.Web.UI.Control value)
0x19f56e  ldarg.1
0x19f56f  newobj   instance void System.Web.UI.WebControls.Image::.ctor()
0x19f574  callvirt instance void LoginContainer::set_PasswordRecoveryIcon(class System.Web.UI.WebControls.Image value)
0x19f579  ldarg.1
0x19f57a  newobj   instance void System.Web.UI.WebControls.Image::.ctor()
0x19f57f  callvirt instance void LoginContainer::set_HelpPageIcon(class System.Web.UI.WebControls.Image value)
0x19f584  ldarg.1
0x19f585  newobj   instance void System.Web.UI.WebControls.Image::.ctor()
0x19f58a  callvirt instance void LoginContainer::set_CreateUserIcon(class System.Web.UI.WebControls.Image value)
0x19f58f  ret
```
