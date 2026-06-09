# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::ParseDeviceInfo

- ea: `0x1bc0`
- end: `0x1c6c`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::ParseDeviceInfo`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a90`

## callees

- `0x1bc0`
- `0x1c70`
- `0x1cd0`

## string_xrefs

- `0x1c1d`: `ItemPath`

## pseudocode

```c

```

## disassembly

```asm
0x1bc0  ldarg.1
0x1bc1  brtrue.s loc_1BC4
0x1bc3  ret
0x1bc4  ldarg.1
0x1bc5  ldstr    aEncoding// "Encoding"
0x1bca  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1bcf  brfalse.s loc_1C13
0x1bd1  ldarg.0
0x1bd2  ldarg.1
0x1bd3  ldstr    aEncoding// "Encoding"
0x1bd8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1bdd  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::GetEncoding(string)
0x1be2  stfld    class [mscorlib]System.Text.Encoding Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_encoding
0x1be7  leave.s  loc_1C13
0x1be9  stloc.0
0x1bea  ldloc.0
0x1beb  call     bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Common.AsynchronousExceptionDetection::IsStoppingException(class [mscorlib]System.Exception)
0x1bf0  brfalse.s loc_1BF4
0x1bf2  rethrow
0x1bf4  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x1bf9  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x1bfe  brfalse.s loc_1C11
0x1c00  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x1c05  ldc.i4.1
0x1c06  ldloc.0
0x1c07  callvirt instance string [mscorlib]System.Object::ToString()
0x1c0c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1c11  leave.s  loc_1C13
0x1c13  ldarg.0
0x1c14  ldc.i4.0
0x1c15  stfld    valuetype DataFeedIdentifierType Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_dataFeedIdentifierType
0x1c1a  ldarg.0
0x1c1b  ldarg.0
0x1c1c  ldarg.1
0x1c1d  ldstr    aItempath// "ItemPath"
0x1c22  call     instance string[] Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::ExtractArrayFromDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo, string key)
0x1c27  stfld    string[] Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_dataFeeds
0x1c2c  ldarg.0
0x1c2d  ldfld    string[] Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_dataFeeds
0x1c32  brfalse.s loc_1C3D
0x1c34  ldarg.0
0x1c35  ldc.i4.2
0x1c36  stfld    valuetype DataFeedIdentifierType Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_dataFeedIdentifierType
0x1c3b  br.s     loc_1C5E
0x1c3d  ldarg.0
0x1c3e  ldarg.0
0x1c3f  ldarg.1
0x1c40  ldstr    aDatafeed// "DataFeed"
0x1c45  call     instance string[] Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::ExtractArrayFromDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo, string key)
0x1c4a  stfld    string[] Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_dataFeeds
0x1c4f  ldarg.0
0x1c50  ldfld    string[] Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_dataFeeds
0x1c55  brfalse.s loc_1C5E
0x1c57  ldarg.0
0x1c58  ldc.i4.1
0x1c59  stfld    valuetype DataFeedIdentifierType Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_dataFeedIdentifierType
0x1c5e  ldarg.0
0x1c5f  ldarg.0
0x1c60  ldarg.1
0x1c61  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::ExtractDataFeedQueriesFromDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo)
0x1c66  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_dataFeedQueries
0x1c6b  ret
```
