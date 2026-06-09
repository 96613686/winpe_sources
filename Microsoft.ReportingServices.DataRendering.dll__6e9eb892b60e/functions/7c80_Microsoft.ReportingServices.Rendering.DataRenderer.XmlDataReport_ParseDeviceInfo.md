# Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::ParseDeviceInfo

- ea: `0x7c80`
- end: `0x7e24`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::ParseDeviceInfo`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x7880`

## callees

- `0x50d0`
- `0x7c80`

## string_xrefs

- `0x7e00`: `FileExtension`
- `0x7df3`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x7c80  ldc.i4.1
0x7c81  stloc.0
0x7c82  ldarg.1
0x7c83  brtrue.s loc_7C87
0x7c85  ldloc.0
0x7c86  ret
0x7c87  ldarg.1
0x7c88  ldstr    aUseformattedva// "UseFormattedValues"
0x7c8d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7c92  brfalse.s loc_7CB3
0x7c94  ldarg.1
0x7c95  ldstr    aUseformattedva// "UseFormattedValues"
0x7c9a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7c9f  ldarg.0
0x7ca0  ldflda   bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_useFormattedValues
0x7ca5  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x7caa  brtrue.s loc_7CB3
0x7cac  ldarg.0
0x7cad  ldc.i4.0
0x7cae  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_useFormattedValues
0x7cb3  ldarg.1
0x7cb4  ldstr    aIndented// "Indented"
0x7cb9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7cbe  brfalse.s loc_7CDF
0x7cc0  ldarg.1
0x7cc1  ldstr    aIndented// "Indented"
0x7cc6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7ccb  ldarg.0
0x7ccc  ldflda   bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_indented
0x7cd1  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x7cd6  brtrue.s loc_7CDF
0x7cd8  ldarg.0
0x7cd9  ldc.i4.0
0x7cda  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_indented
0x7cdf  ldarg.1
0x7ce0  ldstr    aOmitschema// "OmitSchema"
0x7ce5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7cea  brfalse.s loc_7D0B
0x7cec  ldarg.1
0x7ced  ldstr    aOmitschema// "OmitSchema"
0x7cf2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7cf7  ldarg.0
0x7cf8  ldflda   bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_noSchema
0x7cfd  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x7d02  brtrue.s loc_7D0B
0x7d04  ldarg.0
0x7d05  ldc.i4.0
0x7d06  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_noSchema
0x7d0b  ldarg.1
0x7d0c  ldstr    aOmitnamespace// "OmitNamespace"
0x7d11  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7d16  brfalse.s loc_7D37
0x7d18  ldarg.1
0x7d19  ldstr    aOmitnamespace// "OmitNamespace"
0x7d1e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7d23  ldarg.0
0x7d24  ldflda   bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_noNamespace
0x7d29  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x7d2e  brtrue.s loc_7D37
0x7d30  ldarg.0
0x7d31  ldc.i4.0
0x7d32  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_noNamespace
0x7d37  ldarg.1
0x7d38  ldstr    aSchema// "Schema"
0x7d3d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7d42  brfalse.s loc_7D5D
0x7d44  ldarg.1
0x7d45  ldstr    aSchema// "Schema"
0x7d4a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7d4f  ldloca.s 0
0x7d51  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x7d56  brfalse.s loc_7D5D
0x7d58  ldloc.0
0x7d59  ldc.i4.0
0x7d5a  ceq
0x7d5c  stloc.0
0x7d5d  ldarg.1
0x7d5e  ldstr    aEncoding// "Encoding"
0x7d63  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7d68  brfalse.s loc_7DB7
0x7d6a  ldarg.0
0x7d6b  ldarg.1
0x7d6c  ldstr    aEncoding// "Encoding"
0x7d71  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7d76  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::GetEncoding(string)
0x7d7b  stfld    class [mscorlib]System.Text.Encoding Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_encoding
0x7d80  leave.s  loc_7DB7
0x7d82  stloc.1
0x7d83  ldloc.1
0x7d84  call     bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Common.AsynchronousExceptionDetection::IsStoppingException(class [mscorlib]System.Exception)
0x7d89  brfalse.s loc_7D8D
0x7d8b  rethrow
0x7d8d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x7d92  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x7d97  brfalse.s loc_7DAA
0x7d99  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x7d9e  ldc.i4.1
0x7d9f  ldloc.1
0x7da0  callvirt instance string [mscorlib]System.Object::ToString()
0x7da5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x7daa  ldarg.0
0x7dab  ldsfld   class [mscorlib]System.Text.Encoding Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::DefaultEncoding
0x7db0  stfld    class [mscorlib]System.Text.Encoding Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_encoding
0x7db5  leave.s  loc_7DB7
0x7db7  ldarg.0
0x7db8  ldarg.0
0x7db9  ldarg.1
0x7dba  ldstr    aXslt// "XSLT"
0x7dbf  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.DataRendererBase::ExtractStringFromDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo, string key)
0x7dc4  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_outerXSLT
0x7dc9  ldarg.0
0x7dca  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_outerXSLT
0x7dcf  brtrue.s loc_7DD8
0x7dd1  ldarg.0
0x7dd2  ldnull
0x7dd3  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_outerXSLT
0x7dd8  ldarg.0
0x7dd9  ldarg.0
0x7dda  ldarg.1
0x7ddb  ldstr    aMimetype// "MIMEType"
0x7de0  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.DataRendererBase::ExtractStringFromDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo, string key)
0x7de5  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_mimeType
0x7dea  ldarg.0
0x7deb  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_mimeType
0x7df0  brtrue.s loc_7DFD
0x7df2  ldarg.0
0x7df3  ldstr    aTextXml// "text/xml"
0x7df8  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_mimeType
0x7dfd  ldarg.0
0x7dfe  ldarg.0
0x7dff  ldarg.1
0x7e00  ldstr    aFileextension// "FileExtension"
0x7e05  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.DataRendererBase::ExtractStringFromDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo, string key)
0x7e0a  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_dataFileExtension
0x7e0f  ldarg.0
0x7e10  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_dataFileExtension
0x7e15  brtrue.s loc_7E22
0x7e17  ldarg.0
0x7e18  ldstr    aXml// "xml"
0x7e1d  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_dataFileExtension
0x7e22  ldloc.0
0x7e23  ret
```
