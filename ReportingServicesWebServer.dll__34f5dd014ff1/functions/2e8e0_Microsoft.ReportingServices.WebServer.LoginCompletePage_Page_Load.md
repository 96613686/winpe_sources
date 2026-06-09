# Microsoft.ReportingServices.WebServer.LoginCompletePage::Page_Load

- ea: `0x2e8e0`
- end: `0x2e91c`
- name: `Microsoft.ReportingServices.WebServer.LoginCompletePage::Page_Load`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x8f10`
- `0x2e8b0`
- `0x2e8d0`
- `0x35bd0`
- `0x370a0`
- `0x37150`

## string_xrefs

- `0x2e8e1`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.jquery.min.js`
- `0x2e8f1`: `Microsoft.ReportingServices.Rendering.HtmlRenderer.RendererResources.ReportingServicesHybrid.js`

## pseudocode

```c

```

## disassembly

```asm
0x2e8e0  ldarg.0
0x2e8e1  ldstr    aMicrosoftRepor_132// "Microsoft.ReportingServices.Rendering.H"...
0x2e8e6  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x2e8eb  call     instance void Microsoft.ReportingServices.WebServer.LoginCompletePage::set_JQueryUrl(string value)
0x2e8f0  ldarg.0
0x2e8f1  ldstr    aMicrosoftRepor_133// "Microsoft.ReportingServices.Rendering.H"...
0x2e8f6  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x2e8fb  call     instance void Microsoft.ReportingServices.WebServer.LoginCompletePage::set_RSHybridJs(string value)
0x2e900  newobj   instance void Microsoft.ReportingServices.Rendering.Hybrid.UserSettingsAccessor::.ctor()
0x2e905  call     class Microsoft.ReportingServices.Hybrid.OAuth.IAadOAuthProvider Microsoft.ReportingServices.Rendering.Hybrid.OAuthPBIRenderingHelper::GetProvider(class Microsoft.ReportingServices.Rendering.Hybrid.IUserSettingsAccessor settingsAccessor)
0x2e90a  ldarg.0
0x2e90b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2e910  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x2e915  callvirt instance bool Microsoft.ReportingServices.Hybrid.OAuth.IAadOAuthProvider::UpdateToken(class [System]System.Uri uri)
0x2e91a  pop
0x2e91b  ret
```
