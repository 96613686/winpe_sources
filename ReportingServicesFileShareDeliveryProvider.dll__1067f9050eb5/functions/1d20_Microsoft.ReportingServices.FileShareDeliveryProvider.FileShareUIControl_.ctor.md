# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::.ctor

- ea: `0x1d20`
- end: `0x1ed1`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::.ctor`
- size: `433`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x1d2c`: `PathID`
- `0x1d79`: `WriteModeID`

## pseudocode

```c

```

## disassembly

```asm
0x1d20  ldarg.0
0x1d21  ldstr    aFilenameid// "FileNameID"
0x1d26  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::_FileNameID
0x1d2b  ldarg.0
0x1d2c  ldstr    aPathid// "PathID"
0x1d31  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::_PathID
0x1d36  ldarg.0
0x1d37  ldstr    aUsernameid// "UserNameID"
0x1d3c  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::_UserNameID
0x1d41  ldarg.0
0x1d42  ldstr    aPasswordid// "PassWordID"
0x1d47  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::_PassWordID
0x1d4c  ldarg.0
0x1d4d  ldstr    aShadowpassword// "ShadowPassWordID"
0x1d52  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::_ShadowPassWordID
0x1d57  ldarg.0
0x1d58  ldstr    aShadowpassword_0// "ShadowPassWordChangedID"
0x1d5d  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::_ShadowPassWordChangedID
0x1d62  ldarg.0
0x1d63  ldstr    aRenderformatid// "RenderFormatID"
0x1d68  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::_RenderFormatID
0x1d6d  ldarg.0
0x1d6e  ldstr    aFileextnid// "FileExtnID"
0x1d73  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::_FileExtnID
0x1d78  ldarg.0
0x1d79  ldstr    aWritemodeid// "WriteModeID"
0x1d7e  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::_WriteModeID
0x1d83  ldarg.0
0x1d84  ldstr    asc_5248// ""
0x1d89  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_defaultRenderingExtension
0x1d8e  ldarg.0
0x1d8f  ldstr    asc_5248// ""
0x1d94  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ReportName
0x1d99  ldarg.0
0x1d9a  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor()
0x1d9f  stfld    class [System.Web]System.Web.UI.LiteralControl Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_validatorScript
0x1da4  ldarg.0
0x1da5  newobj   instance void [mscorlib]System.Collections.Stack::.ctor()
0x1daa  stfld    class [mscorlib]System.Collections.Stack Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_tableStack
0x1daf  ldarg.0
0x1db0  newobj   instance void [mscorlib]System.Collections.Stack::.ctor()
0x1db5  stfld    class [mscorlib]System.Collections.Stack Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_rowStack
0x1dba  ldarg.0
0x1dbb  newobj   instance void [mscorlib]System.Collections.Stack::.ctor()
0x1dc0  stfld    class [mscorlib]System.Collections.Stack Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_cellStack
0x1dc5  ldarg.0
0x1dc6  ldstr    aScript// "script"
0x1dcb  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x1dd0  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::m_pageLevelScript
0x1dd5  ldarg.0
0x1dd6  newobj   instance void [System.Web]System.Web.UI.WebControls.TextBox::.ctor()
0x1ddb  stfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileName
0x1de0  ldarg.0
0x1de1  newobj   instance void [System.Web]System.Web.UI.WebControls.CheckBox::.ctor()
0x1de6  stfld    class [System.Web]System.Web.UI.WebControls.CheckBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_cbFileExtn
0x1deb  ldarg.0
0x1dec  newobj   instance void [System.Web]System.Web.UI.WebControls.TextBox::.ctor()
0x1df1  stfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPath
0x1df6  ldarg.0
0x1df7  newobj   instance void [System.Web]System.Web.UI.WebControls.TextBox::.ctor()
0x1dfc  stfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtUserName
0x1e01  ldarg.0
0x1e02  newobj   instance void [System.Web]System.Web.UI.WebControls.TextBox::.ctor()
0x1e07  stfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPassWord
0x1e0c  ldarg.0
0x1e0d  newobj   instance void [System.Web]System.Web.UI.WebControls.DropDownList::.ctor()
0x1e12  stfld    class [System.Web]System.Web.UI.WebControls.DropDownList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_ddRenderFormat
0x1e17  ldarg.0
0x1e18  newobj   instance void [System.Web]System.Web.UI.WebControls.RequiredFieldValidator::.ctor()
0x1e1d  stfld    class [System.Web]System.Web.UI.WebControls.RequiredFieldValidator Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_ddRenderFormatRequired
0x1e22  ldarg.0
0x1e23  newobj   instance void [System.Web]System.Web.UI.WebControls.RadioButtonList::.ctor()
0x1e28  stfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbWriteMode
0x1e2d  ldarg.0
0x1e2e  newobj   instance void [System.Web]System.Web.UI.WebControls.PlaceHolder::.ctor()
0x1e33  stfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_invalidFileName
0x1e38  ldarg.0
0x1e39  newobj   instance void [System.Web]System.Web.UI.WebControls.RequiredFieldValidator::.ctor()
0x1e3e  stfld    class [System.Web]System.Web.UI.WebControls.RequiredFieldValidator Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtFileNameRequired
0x1e43  ldarg.0
0x1e44  newobj   instance void [System.Web]System.Web.UI.WebControls.PlaceHolder::.ctor()
0x1e49  stfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_invalidPath
0x1e4e  ldarg.0
0x1e4f  newobj   instance void [System.Web]System.Web.UI.WebControls.RequiredFieldValidator::.ctor()
0x1e54  stfld    class [System.Web]System.Web.UI.WebControls.RequiredFieldValidator Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPathNameRequired
0x1e59  ldarg.0
0x1e5a  newobj   instance void [System.Web]System.Web.UI.WebControls.PlaceHolder::.ctor()
0x1e5f  stfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPassWordReq
0x1e64  ldarg.0
0x1e65  newobj   instance void [System.Web]System.Web.UI.WebControls.RequiredFieldValidator::.ctor()
0x1e6a  stfld    class [System.Web]System.Web.UI.WebControls.RequiredFieldValidator Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtPassWordRequired
0x1e6f  ldarg.0
0x1e70  newobj   instance void [System.Web]System.Web.UI.WebControls.PlaceHolder::.ctor()
0x1e75  stfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtUserNameReq
0x1e7a  ldarg.0
0x1e7b  newobj   instance void [System.Web]System.Web.UI.WebControls.RequiredFieldValidator::.ctor()
0x1e80  stfld    class [System.Web]System.Web.UI.WebControls.RequiredFieldValidator Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_txtUserNameRequired
0x1e85  ldarg.0
0x1e86  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden::.ctor()
0x1e8b  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_shadowPassword
0x1e90  ldarg.0
0x1e91  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden::.ctor()
0x1e96  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_shadowPasswordChanged
0x1e9b  ldarg.0
0x1e9c  newobj   instance void [System.Web]System.Web.UI.WebControls.RadioButtonList::.ctor()
0x1ea1  stfld    class [System.Web]System.Web.UI.WebControls.RadioButtonList Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ui_rbCredentialSelection
0x1ea6  ldarg.0
0x1ea7  call     instance void [System.Web]System.Web.UI.WebControls.WebControl::.ctor()
0x1eac  ldarg.0
0x1ead  ldarg.0
0x1eae  ldftn    instance void Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::Control_Init(object sender, class [mscorlib]System.EventArgs args)
0x1eb4  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1eb9  call     instance void [System.Web]System.Web.UI.Control::add_Init(class [mscorlib]System.EventHandler)
0x1ebe  ldarg.0
0x1ebf  ldarg.0
0x1ec0  ldftn    instance void Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::Control_Load(object sender, class [mscorlib]System.EventArgs e)
0x1ec6  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1ecb  call     instance void [System.Web]System.Web.UI.Control::add_Load(class [mscorlib]System.EventHandler)
0x1ed0  ret
```
