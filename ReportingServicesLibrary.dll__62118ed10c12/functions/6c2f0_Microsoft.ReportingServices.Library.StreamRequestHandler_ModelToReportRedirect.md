# Microsoft.ReportingServices.Library.StreamRequestHandler::ModelToReportRedirect

- ea: `0x6c2f0`
- end: `0x6c37c`
- name: `Microsoft.ReportingServices.Library.StreamRequestHandler::ModelToReportRedirect`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x6c280`

## callees

- `0x6c2f0`

## string_xrefs

- `0x6c331`: `Command`
- `0x6c2f0`: `ReportServiceHttpHandler.ModelToReportRedirect`

## pseudocode

```c

```

## disassembly

```asm
0x6c2f0  ldstr    aReportserviceh// "ReportServiceHttpHandler.ModelToReportR"...
0x6c2f5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x6c2fa  stloc.0
0x6c2fb  ldarg.2
0x6c2fc  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x6c301  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_CatalogParameters()
0x6c306  ldstr    aSessionid_1// "SessionID"
0x6c30b  ldarg.1
0x6c30c  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x6c311  ldarg.2
0x6c312  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x6c317  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_CatalogParameters()
0x6c31c  ldstr    aClearsession// "ClearSession"
0x6c321  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x6c326  ldarg.2
0x6c327  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x6c32c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_CatalogParameters()
0x6c331  ldstr    aCommand_1// "Command"
0x6c336  ldstr    aRender// "Render"
0x6c33b  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x6c340  ldarg.2
0x6c341  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext)
0x6c346  dup
0x6c347  ldarg.2
0x6c348  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x6c34d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_CatalogParameters()
0x6c352  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::AppendCatalogParameters(class [System]System.Collections.Specialized.NameValueCollection)
0x6c357  dup
0x6c358  ldarg.2
0x6c359  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x6c35e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_RenderingParameters()
0x6c363  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::AppendRenderingParameters(class [System]System.Collections.Specialized.NameValueCollection)
0x6c368  callvirt instance string [mscorlib]System.Object::ToString()
0x6c36d  stloc.1
0x6c36e  leave.s  loc_6C37A
0x6c370  ldloc.0
0x6c371  brfalse.s loc_6C379
0x6c373  ldloc.0
0x6c374  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6c379  endfinally
0x6c37a  ldloc.1
0x6c37b  ret
```
