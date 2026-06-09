# Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::RenderModel

- ea: `0x32350`
- end: `0x323d1`
- name: `Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::RenderModel`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x32350`
- `0x323e0`
- `0x32a90`

## string_xrefs

- `0x32350`: `ReportServiceHttpHandler.RenderModel`

## pseudocode

```c

```

## disassembly

```asm
0x32350  ldstr    aReportserviceh_7// "ReportServiceHttpHandler.RenderModel"
0x32355  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x3235a  stloc.0
0x3235b  ldarg.0
0x3235c  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x32361  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x32366  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_EntityIdValue()
0x3236b  brfalse.s loc_323B8
0x3236d  ldarg.0
0x3236e  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x32373  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x32378  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_DrillTypeValue()
0x3237d  brfalse.s loc_323B8
0x3237f  ldarg.0
0x32380  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_Service()
0x32385  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.MemoryThenFileStreamFactory::.ctor()
0x3238a  callvirt instance class [mscorlib]System.IDisposable [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::SetStreamFactory(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamFactoryBase)
0x3238f  stloc.1
0x32390  ldarg.0
0x32391  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_ItemContext()
0x32396  ldarg.0
0x32397  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::get_Service()
0x3239c  ldloca.s 2
0x3239e  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetDrillthroughAction::GetDrillForModel(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService, unsigned int8[]&)
0x323a3  stloc.3
0x323a4  ldarg.0
0x323a5  ldloc.3
0x323a6  ldloc.2
0x323a7  call     instance void Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::HandleTargetReport(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext targetContext, unsigned int8[] targetDefinition)
0x323ac  leave.s  loc_323D0
0x323ae  ldloc.1
0x323af  brfalse.s loc_323B7
0x323b1  ldloc.1
0x323b2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x323b7  endfinally
0x323b8  ldc.i4.1
0x323b9  call     void Microsoft.ReportingServices.WebServer.ReportServiceHttpHandler::EnsureHttpsLevel(valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.HttpsLevel level)
0x323be  ldarg.0
0x323bf  call     instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.StreamRequestHandler::RenderModel()
0x323c4  leave.s  loc_323D0
0x323c6  ldloc.0
0x323c7  brfalse.s loc_323CF
0x323c9  ldloc.0
0x323ca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x323cf  endfinally
0x323d0  ret
```
