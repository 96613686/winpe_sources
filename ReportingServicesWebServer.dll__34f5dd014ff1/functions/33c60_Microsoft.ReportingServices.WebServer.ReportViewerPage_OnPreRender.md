# Microsoft.ReportingServices.WebServer.ReportViewerPage::OnPreRender

- ea: `0x33c60`
- end: `0x33de5`
- name: `Microsoft.ReportingServices.WebServer.ReportViewerPage::OnPreRender`
- size: `389`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callees

- `0x8f10`
- `0x128c0`
- `0x22ec0`
- `0x230a0`
- `0x230c0`
- `0x23160`
- `0x24440`
- `0x33600`
- `0x33c30`
- `0x33c40`
- `0x33c50`
- `0x33c60`
- `0x33e70`
- `0x33e90`
- `0x33ee0`
- `0x33f40`
- `0x344b0`
- `0x370a0`
- `0x37150`
- `0x38040`
- `0x38070`

## string_xrefs

- `0x33d04`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.jquery.min.js`
- `0x33d4c`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.ReportingServicesHybrid.js`
- `0x33ccd`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.Html5Toolbar.css`
- `0x33cf4`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.Html5Renderer.css`
- `0x33d14`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.knockoutjs.js`
- `0x33d24`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.Html5Renderer.js`
- `0x33d3c`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.ReportingServicesHybrid.css`

## pseudocode

```c

```

## disassembly

```asm
0x33c60  ldarg.0
0x33c61  ldstr    aHeadid// "headID"
0x33c66  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.Control::FindControl(string)
0x33c6b  stloc.0
0x33c6c  ldarg.0
0x33c6d  call     instance class Microsoft.ReportingServices.WebServer.ReportViewerHost Microsoft.ReportingServices.WebServer.ReportViewerPage::get_ReportViewer()
0x33c72  stloc.1
0x33c73  ldloc.0
0x33c74  brfalse  loc_33DE4
0x33c79  ldloc.1
0x33c7a  brfalse  loc_33DE4
0x33c7f  ldsfld   string [Microsoft.ReportingServices.HtmlRendering]Microsoft.ReportingServices.Rendering.HtmlRenderer.HTMLElements::Utf8Charset
0x33c84  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0x33c89  stloc.2
0x33c8a  ldloc.0
0x33c8b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x33c90  ldc.i4.0
0x33c91  ldloc.2
0x33c92  callvirt instance void [System.Web]System.Web.UI.ControlCollection::AddAt(int32, class [System.Web]System.Web.UI.Control)
0x33c97  ldarg.0
0x33c98  ldstr    aDoctype// "docType"
0x33c9d  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.Control::FindControl(string)
0x33ca2  castclass [System.Web]System.Web.UI.WebControls.Literal
0x33ca7  ldarg.0
0x33ca8  call     instance string Microsoft.ReportingServices.WebServer.ReportViewerPage::GetDocType()
0x33cad  callvirt instance void [System.Web]System.Web.UI.WebControls.Literal::set_Text(string)
0x33cb2  ldarg.0
0x33cb3  ldstr    aHttpequiv// "httpEquiv"
0x33cb8  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.Control::FindControl(string)
0x33cbd  castclass [System.Web]System.Web.UI.WebControls.Literal
0x33cc2  ldarg.0
0x33cc3  call     instance string Microsoft.ReportingServices.WebServer.ReportViewerPage::GetHttpEquiv()
0x33cc8  callvirt instance void [System.Web]System.Web.UI.WebControls.Literal::set_Text(string)
0x33ccd  ldstr    aMicrosoftRepor_134// "Microsoft.ReportingServices.Rendering.H"...
0x33cd2  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x33cd7  ldloc.0
0x33cd8  call     void Microsoft.ReportingServices.WebServer.ReportViewerPage::AddStylesheet(string url, class [System.Web]System.Web.UI.Control head)
0x33cdd  ldloc.1
0x33cde  callvirt instance class Microsoft.Reporting.WebForms.ServerReport Microsoft.Reporting.WebForms.ReportViewer::get_ServerReport()
0x33ce3  ldloc.1
0x33ce4  callvirt instance string Microsoft.ReportingServices.WebServer.ReportViewerWithV1Styles::get_V1StyleSheetName()
0x33ce9  callvirt instance string Microsoft.Reporting.WebForms.ServerReport::CreateStyleSheetUrl(string styleSheetName)
0x33cee  ldloc.0
0x33cef  call     void Microsoft.ReportingServices.WebServer.ReportViewerPage::AddStylesheet(string url, class [System.Web]System.Web.UI.Control head)
0x33cf4  ldstr    aMicrosoftRepor_135// "Microsoft.ReportingServices.Rendering.H"...
0x33cf9  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x33cfe  ldloc.0
0x33cff  call     void Microsoft.ReportingServices.WebServer.ReportViewerPage::AddStylesheet(string url, class [System.Web]System.Web.UI.Control head)
0x33d04  ldstr    aMicrosoftRepor_132// "Microsoft.ReportingServices.Rendering.H"...
0x33d09  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x33d0e  ldloc.0
0x33d0f  call     void Microsoft.ReportingServices.WebServer.ReportViewerPage::AddJavaScript(string url, class [System.Web]System.Web.UI.Control head)
0x33d14  ldstr    aMicrosoftRepor_136// "Microsoft.ReportingServices.Rendering.H"...
0x33d19  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x33d1e  ldloc.0
0x33d1f  call     void Microsoft.ReportingServices.WebServer.ReportViewerPage::AddJavaScript(string url, class [System.Web]System.Web.UI.Control head)
0x33d24  ldstr    aMicrosoftRepor_137// "Microsoft.ReportingServices.Rendering.H"...
0x33d29  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x33d2e  ldloc.0
0x33d2f  call     void Microsoft.ReportingServices.WebServer.ReportViewerPage::AddJavaScript(string url, class [System.Web]System.Web.UI.Control head)
0x33d34  ldarg.0
0x33d35  call     instance bool Microsoft.ReportingServices.WebServer.ReportViewerPage::get_ShowHybrid()
0x33d3a  brfalse.s loc_33D90
0x33d3c  ldstr    aMicrosoftRepor_138// "Microsoft.ReportingServices.Rendering.H"...
0x33d41  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x33d46  ldloc.0
0x33d47  call     void Microsoft.ReportingServices.WebServer.ReportViewerPage::AddStylesheet(string url, class [System.Web]System.Web.UI.Control head)
0x33d4c  ldstr    aMicrosoftRepor_133// "Microsoft.ReportingServices.Rendering.H"...
0x33d51  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x33d56  ldloc.0
0x33d57  call     void Microsoft.ReportingServices.WebServer.ReportViewerPage::AddJavaScript(string url, class [System.Web]System.Web.UI.Control head)
0x33d5c  newobj   instance void Microsoft.ReportingServices.Rendering.Hybrid.UserSettingsAccessor::.ctor()
0x33d61  call     class Microsoft.ReportingServices.Hybrid.OAuth.IAadOAuthProvider Microsoft.ReportingServices.Rendering.Hybrid.OAuthPBIRenderingHelper::GetProvider(class Microsoft.ReportingServices.Rendering.Hybrid.IUserSettingsAccessor settingsAccessor)
0x33d66  newobj   instance void Microsoft.ReportingServices.Rendering.HtmlRenderer.HybridHtmlSnippets::.ctor(class Microsoft.ReportingServices.Hybrid.OAuth.IAadOAuthProvider provider)
0x33d6b  stloc.3
0x33d6c  call     string Microsoft.ReportingServices.WebServer.ReportViewerHost::GetReportPath()
0x33d71  call     bool Microsoft.ReportingServices.WebServer.ReportViewerPage::HasScheduleReadyDataSources(string itemPath)
0x33d76  stloc.s  4
0x33d78  ldloc.0
0x33d79  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x33d7e  ldloc.3
0x33d7f  ldloc.s  4
0x33d81  callvirt instance string Microsoft.ReportingServices.Rendering.HtmlRenderer.HybridHtmlSnippets::GetPageProperties(bool hasScheduleReadyDataSources)
0x33d86  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0x33d8b  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x33d90  call     bool Microsoft.Reporting.WebForms.ClientTelemetry::get_IsEnabled()
0x33d95  brfalse.s loc_33DDD
0x33d97  ldstr    aMicrosoftRepor_46// "Microsoft.Reporting.WebForms.Scripts.RS"...
0x33d9c  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x33da1  ldloc.0
0x33da2  call     void Microsoft.ReportingServices.WebServer.ReportViewerPage::AddJavaScript(string url, class [System.Web]System.Web.UI.Control head)
0x33da7  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x33dac  newobj   instance void Microsoft.Reporting.WebForms.ClientTelemetry::.ctor(class [System.Web]System.Web.HttpContext context)
0x33db1  stloc.s  5
0x33db3  ldloc.0
0x33db4  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x33db9  ldloc.s  5
0x33dbb  callvirt instance class [System.Web]System.Web.UI.LiteralControl Microsoft.Reporting.WebForms.ClientTelemetry::GetInitJs()
0x33dc0  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x33dc5  ldloc.0
0x33dc6  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x33dcb  ldloc.s  5
0x33dcd  call     string Microsoft.ReportingServices.WebServer.ReportViewerHost::GetReportPath()
0x33dd2  ldc.i4.0
0x33dd3  callvirt instance class [System.Web]System.Web.UI.LiteralControl Microsoft.Reporting.WebForms.ClientTelemetry::GetRenderEvent(string itemPath, bool targetingHtml40)
0x33dd8  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x33ddd  ldarg.0
0x33dde  ldarg.1
0x33ddf  call     instance void [System.Web]System.Web.UI.Control::OnPreRender(class [mscorlib]System.EventArgs)
0x33de4  ret
```
