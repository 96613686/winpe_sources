# Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::.ctor

- ea: `0x2e1d0`
- end: `0x2e2a4`
- name: `Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::.ctor`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x2e1ed`: `hiddenUserDataJson`
- `0x2e280`: `updatePanel`

## pseudocode

```c

```

## disassembly

```asm
0x2e1d0  ldarg.0
0x2e1d1  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlForm::.ctor()
0x2e1d6  dup
0x2e1d7  ldstr    aDeliveryuiform// "deliveryUIForm"
0x2e1dc  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x2e1e1  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlForm Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::Form
0x2e1e6  ldarg.0
0x2e1e7  newobj   instance void [System.Web]System.Web.UI.WebControls.HiddenField::.ctor()
0x2e1ec  dup
0x2e1ed  ldstr    aHiddenuserdata// "hiddenUserDataJson"
0x2e1f2  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x2e1f7  stfld    class [System.Web]System.Web.UI.WebControls.HiddenField Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_hiddenUserDataJson
0x2e1fc  ldarg.0
0x2e1fd  newobj   instance void [System.Web]System.Web.UI.WebControls.HiddenField::.ctor()
0x2e202  dup
0x2e203  ldstr    aHiddenpostoper// "hiddenPostOperation"
0x2e208  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x2e20d  stfld    class [System.Web]System.Web.UI.WebControls.HiddenField Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_hiddenPostOperation
0x2e212  ldarg.0
0x2e213  ldstr    aHtml_0// "Html"
0x2e218  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x2e21d  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_htmlTag
0x2e222  ldarg.0
0x2e223  ldstr    aBody// "Body"
0x2e228  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x2e22d  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_htmlBodyTag
0x2e232  ldarg.0
0x2e233  ldstr    aHead// "Head"
0x2e238  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x2e23d  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_htmlHeadTag
0x2e242  ldarg.0
0x2e243  newobj   instance void [System.Web]System.Web.UI.WebControls.PlaceHolder::.ctor()
0x2e248  dup
0x2e249  ldstr    aDeliveryuiplac// "deliveryUIPlaceHolder"
0x2e24e  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x2e253  stfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_deliveryUIPlaceHolder
0x2e258  ldarg.0
0x2e259  newobj   instance void [System.Web]System.Web.UI.WebControls.Button::.ctor()
0x2e25e  dup
0x2e25f  ldstr    aHiddenformcont// "hiddenFormControl"
0x2e264  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x2e269  stfld    class [System.Web]System.Web.UI.WebControls.Button Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_hiddenFormControlButton
0x2e26e  ldarg.0
0x2e26f  newobj   instance void [System.Web.Extensions]System.Web.UI.ScriptManager::.ctor()
0x2e274  stfld    class [System.Web.Extensions]System.Web.UI.ScriptManager Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_scriptManager
0x2e279  ldarg.0
0x2e27a  newobj   instance void [System.Web.Extensions]System.Web.UI.UpdatePanel::.ctor()
0x2e27f  dup
0x2e280  ldstr    aUpdatepanel// "updatePanel"
0x2e285  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x2e28a  dup
0x2e28b  ldc.i4.1
0x2e28c  callvirt instance void [System.Web.Extensions]System.Web.UI.UpdatePanel::set_UpdateMode(valuetype [System.Web.Extensions]System.Web.UI.UpdatePanelUpdateMode)
0x2e291  dup
0x2e292  ldc.i4.1
0x2e293  callvirt instance void [System.Web.Extensions]System.Web.UI.UpdatePanel::set_ChildrenAsTriggers(bool)
0x2e298  stfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_updatePanel
0x2e29d  ldarg.0
0x2e29e  call     instance void [System.Web]System.Web.UI.Page::.ctor()
0x2e2a3  ret
```
