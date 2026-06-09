# DefaultCompleteStepContentTemplate::ConstructControls

- ea: `0x19dcc0`
- end: `0x19dd7b`
- name: `DefaultCompleteStepContentTemplate::ConstructControls`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, broker_com_uri`

## callers

- `0x19dea0`

## callees

- `0x5f1e0`
- `0x60050`
- `0x936b0`
- `0x936e0`
- `0x93730`
- `0xa0020`
- `0xb9930`
- `0xbaf70`
- `0xbb320`
- `0xbb360`
- `0xbb3f0`
- `0xbd090`
- `0xbd0d0`
- `0xbd160`
- `0x19f0f0`
- `0x19f110`
- `0x19f130`
- `0x19f140`
- `0x19f150`
- `0x19f170`
- `0x19f1b0`
- `0x19f1d0`

## string_xrefs

- `0x19dcdd`: `EditProfileLink`
- `0x19dd09`: `ContinueButtonLinkButton`

## pseudocode

```c

```

## disassembly

```asm
0x19dcc0  ldarg.0
0x19dcc1  call     class System.Web.UI.WebControls.Literal System.Web.UI.WebControls.CreateUserWizard::CreateLiteral()
0x19dcc6  callvirt instance void CompleteStepContainer::set_Title(class System.Web.UI.WebControls.Literal value)
0x19dccb  ldarg.0
0x19dccc  call     class System.Web.UI.WebControls.Literal System.Web.UI.WebControls.CreateUserWizard::CreateLiteral()
0x19dcd1  callvirt instance void CompleteStepContainer::set_SuccessTextLabel(class System.Web.UI.WebControls.Literal value)
0x19dcd6  ldarg.0
0x19dcd7  newobj   instance void System.Web.UI.WebControls.HyperLink::.ctor()
0x19dcdc  dup
0x19dcdd  ldstr    aEditprofilelin_0// "EditProfileLink"
0x19dce2  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19dce7  callvirt instance void CompleteStepContainer::set_EditProfileLink(class System.Web.UI.WebControls.HyperLink value)
0x19dcec  ldarg.0
0x19dced  newobj   instance void System.Web.UI.WebControls.Image::.ctor()
0x19dcf2  callvirt instance void CompleteStepContainer::set_EditProfileIcon(class System.Web.UI.WebControls.Image value)
0x19dcf7  ldarg.0
0x19dcf8  callvirt instance class System.Web.UI.WebControls.Image CompleteStepContainer::get_EditProfileIcon()
0x19dcfd  callvirt instance void System.Web.UI.Control::PreventAutoID()
0x19dd02  ldarg.0
0x19dd03  newobj   instance void System.Web.UI.WebControls.LinkButton::.ctor()
0x19dd08  dup
0x19dd09  ldstr    aContinuebutton_2// "ContinueButtonLinkButton"
0x19dd0e  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19dd13  dup
0x19dd14  ldsfld   string System.Web.UI.WebControls.CreateUserWizard::ContinueButtonCommandName
0x19dd19  callvirt instance void System.Web.UI.WebControls.LinkButton::set_CommandName(string value)
0x19dd1e  dup
0x19dd1f  ldc.i4.0
0x19dd20  callvirt instance void System.Web.UI.WebControls.LinkButton::set_CausesValidation(bool value)
0x19dd25  callvirt instance void CompleteStepContainer::set_ContinueLinkButton(class System.Web.UI.WebControls.LinkButton value)
0x19dd2a  ldarg.0
0x19dd2b  newobj   instance void System.Web.UI.WebControls.Button::.ctor()
0x19dd30  dup
0x19dd31  ldstr    aContinuebutton_3// "ContinueButtonButton"
0x19dd36  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19dd3b  dup
0x19dd3c  ldsfld   string System.Web.UI.WebControls.CreateUserWizard::ContinueButtonCommandName
0x19dd41  callvirt instance void System.Web.UI.WebControls.Button::set_CommandName(string value)
0x19dd46  dup
0x19dd47  ldc.i4.0
0x19dd48  callvirt instance void System.Web.UI.WebControls.Button::set_CausesValidation(bool value)
0x19dd4d  callvirt instance void CompleteStepContainer::set_ContinuePushButton(class System.Web.UI.WebControls.Button value)
0x19dd52  ldarg.0
0x19dd53  newobj   instance void System.Web.UI.WebControls.ImageButton::.ctor()
0x19dd58  dup
0x19dd59  ldstr    aContinuebutton_4// "ContinueButtonImageButton"
0x19dd5e  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19dd63  dup
0x19dd64  ldsfld   string System.Web.UI.WebControls.CreateUserWizard::ContinueButtonCommandName
0x19dd69  callvirt instance void System.Web.UI.WebControls.ImageButton::set_CommandName(string value)
0x19dd6e  dup
0x19dd6f  ldc.i4.0
0x19dd70  callvirt instance void System.Web.UI.WebControls.ImageButton::set_CausesValidation(bool value)
0x19dd75  callvirt instance void CompleteStepContainer::set_ContinueImageButton(class System.Web.UI.WebControls.ImageButton value)
0x19dd7a  ret
```
