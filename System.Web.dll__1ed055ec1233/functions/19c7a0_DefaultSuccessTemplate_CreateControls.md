# DefaultSuccessTemplate::CreateControls

- ea: `0x19c7a0`
- end: `0x19c85b`
- name: `DefaultSuccessTemplate::CreateControls`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops`

## callers

- `0x19ca00`

## callees

- `0x5f1e0`
- `0x936b0`
- `0x936e0`
- `0x93730`
- `0xb9930`
- `0xbaf70`
- `0xbb320`
- `0xbb360`
- `0xbb3f0`
- `0xbd090`
- `0xbd0d0`
- `0xbd160`
- `0xbf6d0`
- `0x19ca50`
- `0x19ca70`
- `0x19ca90`
- `0x19cac0`
- `0x19cad0`
- `0x19cae0`
- `0x19cb00`
- `0x19cb20`

## string_xrefs

- `0x19c7c7`: `EditProfileLinkSuccess`
- `0x19c7e3`: `ContinueLinkButton`

## pseudocode

```c

```

## disassembly

```asm
0x19c7a0  ldarg.1
0x19c7a1  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x19c7a6  callvirt instance void SuccessContainer::set_Title(class System.Web.UI.WebControls.Literal value)
0x19c7ab  ldarg.1
0x19c7ac  newobj   instance void System.Web.UI.WebControls.Literal::.ctor()
0x19c7b1  callvirt instance void SuccessContainer::set_SuccessTextLabel(class System.Web.UI.WebControls.Literal value)
0x19c7b6  ldarg.1
0x19c7b7  newobj   instance void System.Web.UI.WebControls.HyperLink::.ctor()
0x19c7bc  callvirt instance void SuccessContainer::set_EditProfileLink(class System.Web.UI.WebControls.HyperLink value)
0x19c7c1  ldarg.1
0x19c7c2  callvirt instance class System.Web.UI.WebControls.HyperLink SuccessContainer::get_EditProfileLink()
0x19c7c7  ldstr    aEditprofilelin// "EditProfileLinkSuccess"
0x19c7cc  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19c7d1  ldarg.1
0x19c7d2  newobj   instance void System.Web.UI.WebControls.Image::.ctor()
0x19c7d7  callvirt instance void SuccessContainer::set_EditProfileIcon(class System.Web.UI.WebControls.Image value)
0x19c7dc  newobj   instance void System.Web.UI.WebControls.LinkButton::.ctor()
0x19c7e1  stloc.0
0x19c7e2  ldloc.0
0x19c7e3  ldstr    aContinuelinkbu// "ContinueLinkButton"
0x19c7e8  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19c7ed  ldloc.0
0x19c7ee  ldsfld   string System.Web.UI.WebControls.ChangePassword::ContinueButtonCommandName
0x19c7f3  callvirt instance void System.Web.UI.WebControls.LinkButton::set_CommandName(string value)
0x19c7f8  ldloc.0
0x19c7f9  ldc.i4.0
0x19c7fa  callvirt instance void System.Web.UI.WebControls.LinkButton::set_CausesValidation(bool value)
0x19c7ff  ldarg.1
0x19c800  ldloc.0
0x19c801  callvirt instance void SuccessContainer::set_ContinueLinkButton(class System.Web.UI.WebControls.LinkButton value)
0x19c806  newobj   instance void System.Web.UI.WebControls.ImageButton::.ctor()
0x19c80b  stloc.1
0x19c80c  ldloc.1
0x19c80d  ldstr    aContinueimageb// "ContinueImageButton"
0x19c812  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19c817  ldloc.1
0x19c818  ldsfld   string System.Web.UI.WebControls.ChangePassword::ContinueButtonCommandName
0x19c81d  callvirt instance void System.Web.UI.WebControls.ImageButton::set_CommandName(string value)
0x19c822  ldloc.1
0x19c823  ldc.i4.0
0x19c824  callvirt instance void System.Web.UI.WebControls.ImageButton::set_CausesValidation(bool value)
0x19c829  ldarg.1
0x19c82a  ldloc.1
0x19c82b  callvirt instance void SuccessContainer::set_ContinueImageButton(class System.Web.UI.WebControls.ImageButton value)
0x19c830  newobj   instance void System.Web.UI.WebControls.Button::.ctor()
0x19c835  stloc.2
0x19c836  ldloc.2
0x19c837  ldstr    aContinuepushbu// "ContinuePushButton"
0x19c83c  callvirt instance void System.Web.UI.Control::set_ID(string value)
0x19c841  ldloc.2
0x19c842  ldsfld   string System.Web.UI.WebControls.ChangePassword::ContinueButtonCommandName
0x19c847  callvirt instance void System.Web.UI.WebControls.Button::set_CommandName(string value)
0x19c84c  ldloc.2
0x19c84d  ldc.i4.0
0x19c84e  callvirt instance void System.Web.UI.WebControls.Button::set_CausesValidation(bool value)
0x19c853  ldarg.1
0x19c854  ldloc.2
0x19c855  callvirt instance void SuccessContainer::set_ContinuePushButton(class System.Web.UI.WebControls.Button value)
0x19c85a  ret
```
