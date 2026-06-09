# Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::Page_PreInit

- ea: `0x2e310`
- end: `0x2e480`
- name: `Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::Page_PreInit`
- size: `368`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x8f10`
- `0x2e2d0`
- `0x2e2f0`
- `0x2e310`
- `0x2e570`
- `0x2e760`
- `0x2e7b0`

## string_xrefs

- `0x2e335`: `extension Name`
- `0x2e3f3`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.ReportingServices.js`

## pseudocode

```c

```

## disassembly

```asm
0x2e310  ldarg.0
0x2e311  call     instance string Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::get_DeliveryExtensionName()
0x2e316  stloc.0
0x2e317  ldloc.0
0x2e318  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e31d  brtrue.s loc_2E335
0x2e31f  ldarg.0
0x2e320  call     instance string Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::get_ItemPath()
0x2e325  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e32a  brtrue.s loc_2E335
0x2e32c  ldarg.0
0x2e32d  ldloc.0
0x2e32e  call     instance bool Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::LoadDeliveryExtensionUI(string deliveryID)
0x2e333  brtrue.s loc_2E340
0x2e335  ldstr    aExtensionName// "extension Name"
0x2e33a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string)
0x2e33f  throw
0x2e340  ldarg.0
0x2e341  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_updatePanel
0x2e346  callvirt instance class [System.Web]System.Web.UI.Control [System.Web.Extensions]System.Web.UI.UpdatePanel::get_ContentTemplateContainer()
0x2e34b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2e350  ldarg.0
0x2e351  ldfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_deliveryUIPlaceHolder
0x2e356  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2e35b  ldarg.0
0x2e35c  ldfld    class [System.Web]System.Web.UI.WebControls.Button Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_hiddenFormControlButton
0x2e361  ldstr    aHidden// "hidden"
0x2e366  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0x2e36b  ldarg.0
0x2e36c  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_updatePanel
0x2e371  callvirt instance class [System.Web]System.Web.UI.Control [System.Web.Extensions]System.Web.UI.UpdatePanel::get_ContentTemplateContainer()
0x2e376  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2e37b  ldarg.0
0x2e37c  ldfld    class [System.Web]System.Web.UI.WebControls.HiddenField Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_hiddenUserDataJson
0x2e381  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2e386  ldarg.0
0x2e387  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_updatePanel
0x2e38c  callvirt instance class [System.Web]System.Web.UI.Control [System.Web.Extensions]System.Web.UI.UpdatePanel::get_ContentTemplateContainer()
0x2e391  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2e396  ldarg.0
0x2e397  ldfld    class [System.Web]System.Web.UI.WebControls.HiddenField Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_hiddenPostOperation
0x2e39c  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2e3a1  ldarg.0
0x2e3a2  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_updatePanel
0x2e3a7  callvirt instance class [System.Web]System.Web.UI.Control [System.Web.Extensions]System.Web.UI.UpdatePanel::get_ContentTemplateContainer()
0x2e3ac  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2e3b1  ldarg.0
0x2e3b2  ldfld    class [System.Web]System.Web.UI.WebControls.Button Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_hiddenFormControlButton
0x2e3b7  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2e3bc  ldarg.0
0x2e3bd  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlForm Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::Form
0x2e3c2  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2e3c7  ldarg.0
0x2e3c8  ldfld    class [System.Web.Extensions]System.Web.UI.ScriptManager Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_scriptManager
0x2e3cd  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2e3d2  ldarg.0
0x2e3d3  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlForm Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::Form
0x2e3d8  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2e3dd  ldarg.0
0x2e3de  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_updatePanel
0x2e3e3  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2e3e8  ldarg.0
0x2e3e9  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_htmlHeadTag
0x2e3ee  call     void Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::AddReportingServicesCss(class [System.Web]System.Web.UI.Control head)
0x2e3f3  ldstr    aMicrosoftRepor_130// "Microsoft.ReportingServices.Rendering.H"...
0x2e3f8  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x2e3fd  ldarg.0
0x2e3fe  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_htmlHeadTag
0x2e403  call     void Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::AddJavaScript(string url, class [System.Web]System.Web.UI.Control head)
0x2e408  ldarg.0
0x2e409  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_htmlBodyTag
0x2e40e  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2e413  ldarg.0
0x2e414  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlForm Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::Form
0x2e419  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2e41e  ldarg.0
0x2e41f  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_htmlTag
0x2e424  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2e429  ldarg.0
0x2e42a  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_htmlHeadTag
0x2e42f  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2e434  ldarg.0
0x2e435  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_htmlTag
0x2e43a  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2e43f  ldarg.0
0x2e440  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_htmlBodyTag
0x2e445  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2e44a  ldarg.0
0x2e44b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_htmlTag
0x2e450  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2e455  ldstr    aLang// "lang"
0x2e45a  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2e45f  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentUICulture()
0x2e464  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x2e469  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2e46e  ldarg.0
0x2e46f  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2e474  ldarg.0
0x2e475  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_htmlTag
0x2e47a  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2e47f  ret
```
