# Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::ParseDeviceInfo

- ea: `0x4c10`
- end: `0x4dd1`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::ParseDeviceInfo`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x4a00`

## callees

- `0x4c10`
- `0x50d0`

## string_xrefs

- `0x4d25`: `FileExtension`
- `0x4d3f`: `Extension`

## pseudocode

```c

```

## disassembly

```asm
0x4c10  ldarg.1
0x4c11  brtrue.s loc_4C14
0x4c13  ret
0x4c14  ldarg.1
0x4c15  ldstr    aExcelmode// "ExcelMode"
0x4c1a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4c1f  brfalse.s loc_4C40
0x4c21  ldarg.1
0x4c22  ldstr    aExcelmode// "ExcelMode"
0x4c27  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4c2c  ldarg.0
0x4c2d  ldflda   bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_excelMode
0x4c32  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x4c37  brtrue.s loc_4C40
0x4c39  ldarg.0
0x4c3a  ldc.i4.1
0x4c3b  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_excelMode
0x4c40  ldarg.0
0x4c41  ldarg.0
0x4c42  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_excelMode
0x4c47  ldc.i4.0
0x4c48  cgt.un
0x4c4a  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_useFormattedValues
0x4c4f  ldarg.1
0x4c50  ldstr    aUseformattedva// "UseFormattedValues"
0x4c55  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4c5a  brfalse.s loc_4C7B
0x4c5c  ldarg.1
0x4c5d  ldstr    aUseformattedva// "UseFormattedValues"
0x4c62  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4c67  ldarg.0
0x4c68  ldflda   bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_useFormattedValues
0x4c6d  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x4c72  brtrue.s loc_4C7B
0x4c74  ldarg.0
0x4c75  ldc.i4.0
0x4c76  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_useFormattedValues
0x4c7b  ldarg.1
0x4c7c  ldstr    aNoheader// "NoHeader"
0x4c81  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4c86  brfalse.s loc_4CA7
0x4c88  ldarg.1
0x4c89  ldstr    aNoheader// "NoHeader"
0x4c8e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4c93  ldarg.0
0x4c94  ldflda   bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_noHeader
0x4c99  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x4c9e  brtrue.s loc_4CA7
0x4ca0  ldarg.0
0x4ca1  ldc.i4.0
0x4ca2  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_noHeader
0x4ca7  ldarg.1
0x4ca8  ldstr    aSuppresslinebr// "SuppressLineBreaks"
0x4cad  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4cb2  brfalse.s loc_4CD3
0x4cb4  ldarg.1
0x4cb5  ldstr    aSuppresslinebr// "SuppressLineBreaks"
0x4cba  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4cbf  ldarg.0
0x4cc0  ldflda   bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_suppressLineBreaks
0x4cc5  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x4cca  brtrue.s loc_4CD3
0x4ccc  ldarg.0
0x4ccd  ldc.i4.0
0x4cce  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_suppressLineBreaks
0x4cd3  ldarg.1
0x4cd4  ldstr    aEncoding// "Encoding"
0x4cd9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4cde  brfalse.s loc_4D22
0x4ce0  ldarg.0
0x4ce1  ldarg.1
0x4ce2  ldstr    aEncoding// "Encoding"
0x4ce7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4cec  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::GetEncoding(string)
0x4cf1  stfld    class [mscorlib]System.Text.Encoding Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_encoding
0x4cf6  leave.s  loc_4D22
0x4cf8  stloc.0
0x4cf9  ldloc.0
0x4cfa  call     bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Common.AsynchronousExceptionDetection::IsStoppingException(class [mscorlib]System.Exception)
0x4cff  brfalse.s loc_4D03
0x4d01  rethrow
0x4d03  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x4d08  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x4d0d  brfalse.s loc_4D20
0x4d0f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x4d14  ldc.i4.1
0x4d15  ldloc.0
0x4d16  callvirt instance string [mscorlib]System.Object::ToString()
0x4d1b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4d20  leave.s  loc_4D22
0x4d22  ldarg.0
0x4d23  ldarg.0
0x4d24  ldarg.1
0x4d25  ldstr    aFileextension// "FileExtension"
0x4d2a  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.DataRendererBase::ExtractStringFromDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo, string key)
0x4d2f  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_fileExtension
0x4d34  ldarg.0
0x4d35  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_fileExtension
0x4d3a  brtrue.s loc_4D61
0x4d3c  ldarg.0
0x4d3d  ldarg.0
0x4d3e  ldarg.1
0x4d3f  ldstr    aExtension// "Extension"
0x4d44  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.DataRendererBase::ExtractStringFromDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo, string key)
0x4d49  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_fileExtension
0x4d4e  ldarg.0
0x4d4f  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_fileExtension
0x4d54  brtrue.s loc_4D61
0x4d56  ldarg.0
0x4d57  ldstr    aCsv// "csv"
0x4d5c  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_fileExtension
0x4d61  ldarg.0
0x4d62  ldarg.0
0x4d63  ldarg.1
0x4d64  ldstr    aQualifier// "Qualifier"
0x4d69  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.DataRendererBase::ExtractStringFromDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo, string key)
0x4d6e  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_qualifier
0x4d73  ldarg.0
0x4d74  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_qualifier
0x4d79  brtrue.s loc_4D86
0x4d7b  ldarg.0
0x4d7c  ldstr    asc_F5FC// "\""
0x4d81  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_qualifier
0x4d86  ldarg.0
0x4d87  ldarg.0
0x4d88  ldarg.1
0x4d89  ldstr    aRecorddelimite// "RecordDelimiter"
0x4d8e  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.DataRendererBase::ExtractStringFromDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo, string key)
0x4d93  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_recordDelimiter
0x4d98  ldarg.0
0x4d99  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_recordDelimiter
0x4d9e  brtrue.s loc_4DAB
0x4da0  ldarg.0
0x4da1  ldstr    asc_F620// "\r\n"
0x4da6  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_recordDelimiter
0x4dab  ldarg.0
0x4dac  ldarg.0
0x4dad  ldarg.1
0x4dae  ldstr    aFielddelimiter// "FieldDelimiter"
0x4db3  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.DataRendererBase::ExtractStringFromDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo, string key)
0x4db8  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_fieldDelimiter
0x4dbd  ldarg.0
0x4dbe  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_fieldDelimiter
0x4dc3  brtrue.s loc_4DD0
0x4dc5  ldarg.0
0x4dc6  ldstr    asc_F644// ","
0x4dcb  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.CsvReport::m_fieldDelimiter
0x4dd0  ret
```
