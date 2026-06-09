# Microsoft.ReportingServices.Rendering.DataRenderer.AtomSchemaVisitor::BuildBaseUrl

- ea: `0x2b80`
- end: `0x2bba`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomSchemaVisitor::BuildBaseUrl`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2be0`

## string_xrefs

- `0x2b8d`: `Command`

## pseudocode

```c

```

## disassembly

```asm
0x2b80  ldarg.1
0x2b81  ldc.i4.1
0x2b82  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::GetReportUrl(bool)
0x2b87  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::.ctor(string)
0x2b8c  dup
0x2b8d  ldstr    aCommand// "Command"
0x2b92  ldstr    aRender// "Render"
0x2b97  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::AppendCatalogParameter(string, string)
0x2b9c  ldarg.2
0x2b9d  ldstr    aFormat// "Format"
0x2ba2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2ba7  stloc.0
0x2ba8  dup
0x2ba9  ldstr    aFormat// "Format"
0x2bae  ldloc.0
0x2baf  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::AppendCatalogParameter(string, string)
0x2bb4  callvirt instance string [mscorlib]System.Object::ToString()
0x2bb9  ret
```
