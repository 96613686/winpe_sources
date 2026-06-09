# Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::AddReportingServicesCss

- ea: `0x2e760`
- end: `0x2e7ad`
- name: `Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::AddReportingServicesCss`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x2e310`

## callees

- `0x8f10`

## string_xrefs

- `0x2e767`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.ReportingServices.css`

## pseudocode

```c

```

## disassembly

```asm
0x2e760  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlLink::.ctor()
0x2e765  stloc.0
0x2e766  ldloc.0
0x2e767  ldstr    aMicrosoftRepor_131// "Microsoft.ReportingServices.Rendering.H"...
0x2e76c  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x2e771  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlLink::set_Href(string)
0x2e776  ldloc.0
0x2e777  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2e77c  ldstr    aRel// "rel"
0x2e781  ldstr    aStylesheet_0// "stylesheet"
0x2e786  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2e78b  ldloc.0
0x2e78c  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x2e791  ldstr    aType// "type"
0x2e796  ldstr    aTextCss// "text/css"
0x2e79b  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2e7a0  ldarg.0
0x2e7a1  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2e7a6  ldloc.0
0x2e7a7  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2e7ac  ret
```
