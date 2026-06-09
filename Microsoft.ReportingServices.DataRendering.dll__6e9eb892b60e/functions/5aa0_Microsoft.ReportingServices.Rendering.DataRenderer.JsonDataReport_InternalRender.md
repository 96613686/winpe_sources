# Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataReport::InternalRender

- ea: `0x5aa0`
- end: `0x5b20`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataReport::InternalRender`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x260`
- `0x5430`
- `0x5aa0`
- `0x5b20`
- `0x5bf0`
- `0x6040`
- `0x6c00`
- `0x6f70`

## string_xrefs

- `0x5acc`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x5aa0  ldarg.0
0x5aa1  ldarg.3
0x5aa2  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataReport::ParseDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo)
0x5aa7  ldarg.0
0x5aa8  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataReport::useSharedDataSetTableHandler
0x5aad  brtrue.s loc_5ABA
0x5aaf  call     string Microsoft.ReportingServices.DataRendering.StringResources::get_rrJsonRenderOutputNotSupported()
0x5ab4  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(string)
0x5ab9  throw
0x5aba  ldarg.s  5
0x5abc  ldarg.1
0x5abd  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_Name()
0x5ac2  ldstr    aJson// "json"
0x5ac7  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x5acc  ldstr    aApplicationJso// "application/json"
0x5ad1  ldc.i4.0
0x5ad2  ldc.i4.0
0x5ad3  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CreateAndRegisterStream::Invoke(string, string, class [mscorlib]System.Text.Encoding, string, bool, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.StreamOper)
0x5ad8  dup
0x5ad9  ldarg.0
0x5ada  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataReport::indented
0x5adf  ldarg.0
0x5ae0  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataReport::useMsDateFormat
0x5ae5  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x5aea  ldarg.0
0x5aeb  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataReport::useSharedDataSetTableHandler
0x5af0  ldc.i4.0
0x5af1  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::.ctor(class [mscorlib]System.IO.Stream outputStream, bool indented, bool useMsDateFormat, class [mscorlib]System.Text.Encoding encoding, bool treatDecimalAsDouble, [opt] bool escapeUnicode)
0x5af6  ldarg.0
0x5af7  ldfld    valuetype [mscorlib]System.Nullable`1<int32> Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataReport::maxRows
0x5afc  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor visitor, valuetype [mscorlib]System.Nullable`1<int32> maxRows)
0x5b01  stloc.0
0x5b02  ldloc.0
0x5b03  ldloc.0
0x5b04  ldloc.0
0x5b05  ldloc.0
0x5b06  ldc.i4.1
0x5b07  ldc.i4.0
0x5b08  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x5b0d  ldarg.1
0x5b0e  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReport(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report)
0x5b13  ldloc.0
0x5b14  ldarg.1
0x5b15  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::OnReportEnd(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report)
0x5b1a  callvirt instance void [mscorlib]System.IO.Stream::Flush()
0x5b1f  ret
```
