# Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::InternalRender

- ea: `0x4a00`
- end: `0x4c01`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::InternalRender`
- size: `513`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x240`
- `0x2e0`
- `0x300`
- `0x3fe0`
- `0x4010`
- `0x4050`
- `0x4420`
- `0x4a00`
- `0x4c10`
- `0x4e40`
- `0x4f30`
- `0x6c00`
- `0x6d00`
- `0x6d60`
- `0x6f70`

## pseudocode

```c

```

## disassembly

```asm
0x4a00  ldarg.0
0x4a01  ldarg.3
0x4a02  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::ParseDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo)
0x4a07  ldarg.0
0x4a08  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_fieldDelimiter
0x4a0d  ldarg.0
0x4a0e  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_recordDelimiter
0x4a13  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4a18  brfalse.s loc_4A25
0x4a1a  call     string Microsoft.ReportingServices.DataRendering.StringResources::get_rrSameDelimiterError()
0x4a1f  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(string)
0x4a24  throw
0x4a25  ldarg.0
0x4a26  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_qualifier
0x4a2b  ldarg.0
0x4a2c  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_fieldDelimiter
0x4a31  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4a36  brtrue.s loc_4A4B
0x4a38  ldarg.0
0x4a39  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_qualifier
0x4a3e  ldarg.0
0x4a3f  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_recordDelimiter
0x4a44  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4a49  brfalse.s loc_4A56
0x4a4b  call     string Microsoft.ReportingServices.DataRendering.StringResources::get_rrSameQualiferDelimiterError()
0x4a50  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(string)
0x4a55  throw
0x4a56  ldarg.0
0x4a57  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_qualifier
0x4a5c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4a61  ldc.i4.0
0x4a62  ble.s    loc_4A8F
0x4a64  ldarg.0
0x4a65  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_suppressLineBreaks
0x4a6a  brfalse.s loc_4A9A
0x4a6c  ldarg.0
0x4a6d  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_qualifier
0x4a72  callvirt instance string [mscorlib]System.String::Trim()
0x4a77  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4a7c  ldc.i4.0
0x4a7d  ble.s    loc_4A8F
0x4a7f  ldarg.0
0x4a80  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_qualifier
0x4a85  ldc.i4.s 0xA
0x4a87  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x4a8c  ldc.i4.0
0x4a8d  blt.s    loc_4A9A
0x4a8f  call     string Microsoft.ReportingServices.DataRendering.StringResources::get_rrInvalidQualifier()
0x4a94  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(string)
0x4a99  throw
0x4a9a  ldarg.s  5
0x4a9c  ldarg.1
0x4a9d  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_Name()
0x4aa2  ldarg.0
0x4aa3  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_fileExtension
0x4aa8  ldarg.0
0x4aa9  ldfld    class [mscorlib]System.Text.Encoding Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_encoding
0x4aae  ldarg.0
0x4aaf  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_mimeType
0x4ab4  ldc.i4.0
0x4ab5  ldc.i4.0
0x4ab6  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CreateAndRegisterStream::Invoke(string, string, class [mscorlib]System.Text.Encoding, string, bool, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.StreamOper)
0x4abb  stloc.0
0x4abc  ldloc.0
0x4abd  ldarg.0
0x4abe  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_fieldDelimiter
0x4ac3  ldarg.0
0x4ac4  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_recordDelimiter
0x4ac9  ldarg.0
0x4aca  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_qualifier
0x4acf  ldarg.0
0x4ad0  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_suppressLineBreaks
0x4ad5  ldarg.0
0x4ad6  ldfld    class [mscorlib]System.Text.Encoding Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_encoding
0x4adb  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::.ctor(class [mscorlib]System.IO.Stream outputStream, string fieldDelimiter, string recordDelimiter, string qualifier, bool suppressLineBreaks, class [mscorlib]System.Text.Encoding encoding)
0x4ae0  stloc.1
0x4ae1  ldloc.1
0x4ae2  ldarg.0
0x4ae3  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_noHeader
0x4ae8  ldarg.0
0x4ae9  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_excelMode
0x4aee  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor csvVisitor, bool noHeaders, bool excelMode)
0x4af3  stloc.2
0x4af4  ldloc.2
0x4af5  ldloc.2
0x4af6  ldloc.2
0x4af7  ldloc.2
0x4af8  ldc.i4.0
0x4af9  ldarg.0
0x4afa  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_excelMode
0x4aff  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x4b04  stloc.3
0x4b05  ldloc.3
0x4b06  ldarg.1
0x4b07  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReport(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report)
0x4b0c  ldloc.2
0x4b0d  callvirt instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::get_Columns()
0x4b12  ldloc.2
0x4b13  callvirt instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::get_HeaderOnlyColumns()
0x4b18  sub
0x4b19  ldc.i4.0
0x4b1a  ble.s    loc_4B4A
0x4b1c  ldloc.1
0x4b1d  ldarg.0
0x4b1e  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_excelMode
0x4b23  ldarg.0
0x4b24  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_useFormattedValues
0x4b29  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor csvVisitor, bool stackedMode, bool useFormattedValues)
0x4b2e  stloc.s  4
0x4b30  ldloc.s  4
0x4b32  ldloc.s  4
0x4b34  ldloc.s  4
0x4b36  ldloc.s  4
0x4b38  ldc.i4.1
0x4b39  ldarg.0
0x4b3a  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_excelMode
0x4b3f  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x4b44  ldarg.1
0x4b45  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReport(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report)
0x4b4a  ldarg.0
0x4b4b  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_excelMode
0x4b50  brfalse  loc_4BFA
0x4b55  ldloc.3
0x4b56  callvirt instance class [mscorlib]System.Collections.IEnumerator Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::get_TopLevelDataRegionsOrMaps()
0x4b5b  stloc.s  5
0x4b5d  br       loc_4BEE
0x4b62  ldloc.1
0x4b63  ldarg.0
0x4b64  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_noHeader
0x4b69  ldarg.0
0x4b6a  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_excelMode
0x4b6f  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor csvVisitor, bool noHeaders, bool excelMode)
0x4b74  stloc.s  6
0x4b76  ldloc.s  6
0x4b78  ldloc.s  6
0x4b7a  ldloc.s  6
0x4b7c  ldloc.s  6
0x4b7e  ldc.i4.0
0x4b7f  ldc.i4.0
0x4b80  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x4b85  ldloc.s  5
0x4b87  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4b8c  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem
0x4b91  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkDataRegionOrMap(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem)
0x4b96  ldloc.s  6
0x4b98  callvirt instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::get_Columns()
0x4b9d  ldloc.s  6
0x4b9f  callvirt instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::get_HeaderOnlyColumns()
0x4ba4  sub
0x4ba5  ldc.i4.0
0x4ba6  ble.s    loc_4BDE
0x4ba8  ldloc.1
0x4ba9  ldarg.0
0x4baa  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_excelMode
0x4baf  ldarg.0
0x4bb0  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_useFormattedValues
0x4bb5  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvHandler::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor csvVisitor, bool stackedMode, bool useFormattedValues)
0x4bba  stloc.s  7
0x4bbc  ldloc.s  7
0x4bbe  ldloc.s  7
0x4bc0  ldloc.s  7
0x4bc2  ldloc.s  7
0x4bc4  ldc.i4.1
0x4bc5  ldc.i4.0
0x4bc6  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x4bcb  ldloc.s  5
0x4bcd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4bd2  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem
0x4bd7  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkDataRegionOrMap(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem)
0x4bdc  br.s     loc_4BEE
0x4bde  ldloc.s  6
0x4be0  callvirt instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::get_HeaderOnlyColumns()
0x4be5  ldc.i4.0
0x4be6  ble.s    loc_4BEE
0x4be8  ldloc.1
0x4be9  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvVisitor::EndRegion()
0x4bee  ldloc.s  5
0x4bf0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4bf5  brtrue   loc_4B62
0x4bfa  ldloc.0
0x4bfb  callvirt instance void [mscorlib]System.IO.Stream::Flush()
0x4c00  ret
```
