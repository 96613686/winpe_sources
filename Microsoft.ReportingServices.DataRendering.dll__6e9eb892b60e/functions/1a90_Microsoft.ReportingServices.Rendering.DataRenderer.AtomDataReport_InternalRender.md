# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::InternalRender

- ea: `0x1a90`
- end: `0x1bbb`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::InternalRender`
- size: `299`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1a50`
- `0x1a90`
- `0x1bc0`
- `0x1cf0`
- `0x1d70`
- `0x1e90`
- `0x2110`
- `0x2300`

## string_xrefs

- `0x1ac2`: `application/atomsvc+xml`
- `0x1ada`: `application/atom+xml`
- `0x1af2`: `application/xml`

## pseudocode

```c

```

## disassembly

```asm
0x1a90  ldarg.0
0x1a91  ldarg.3
0x1a92  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::ParseDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo)
0x1a97  ldarg.0
0x1a98  call     instance valuetype RenderingMode Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::get_Mode()
0x1a9d  stloc.1
0x1a9e  ldloc.1
0x1a9f  switch   loc_1AB6, loc_1ACE, loc_1AE6, loc_1AFE
0x1ab4  br.s     loc_1B14
0x1ab6  ldarg.0
0x1ab7  ldstr    aAtomsvc// "atomsvc"
0x1abc  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_fileExtension
0x1ac1  ldarg.0
0x1ac2  ldstr    aApplicationAto// "application/atomsvc+xml"
0x1ac7  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_mimeType
0x1acc  br.s     loc_1B14
0x1ace  ldarg.0
0x1acf  ldstr    aAtom// "atom"
0x1ad4  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_fileExtension
0x1ad9  ldarg.0
0x1ada  ldstr    aApplicationAto_0// "application/atom+xml"
0x1adf  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_mimeType
0x1ae4  br.s     loc_1B14
0x1ae6  ldarg.0
0x1ae7  ldstr    aXml// "xml"
0x1aec  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_fileExtension
0x1af1  ldarg.0
0x1af2  ldstr    aApplicationXml// "application/xml"
0x1af7  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_mimeType
0x1afc  br.s     loc_1B14
0x1afe  ldarg.0
0x1aff  ldstr    aTxt// "txt"
0x1b04  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_fileExtension
0x1b09  ldarg.0
0x1b0a  ldstr    aMultipartMixed// "multipart/mixed; boundary=batch_36522ad"...
0x1b0f  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_mimeType
0x1b14  ldarg.s  5
0x1b16  ldarg.1
0x1b17  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_Name()
0x1b1c  ldarg.0
0x1b1d  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_fileExtension
0x1b22  ldarg.0
0x1b23  ldfld    class [mscorlib]System.Text.Encoding Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_encoding
0x1b28  ldarg.0
0x1b29  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_mimeType
0x1b2e  ldc.i4.0
0x1b2f  ldc.i4.0
0x1b30  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CreateAndRegisterStream::Invoke(string, string, class [mscorlib]System.Text.Encoding, string, bool, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.StreamOper)
0x1b35  stloc.0
0x1b36  ldarg.0
0x1b37  call     instance valuetype RenderingMode Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::get_Mode()
0x1b3c  ldc.i4.3
0x1b3d  bne.un.s loc_1B50
0x1b3f  ldarg.0
0x1b40  ldloc.0
0x1b41  ldarg.1
0x1b42  ldarg.2
0x1b43  ldarg.0
0x1b44  ldfld    string[] Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_dataFeeds
0x1b49  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteBatch(class [mscorlib]System.IO.Stream outputStream, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report, class [System]System.Collections.Specialized.NameValueCollection reportServerParameters, string[] dataFeeds)
0x1b4e  br.s     loc_1BB4
0x1b50  ldarg.0
0x1b51  ldloc.0
0x1b52  ldc.i4.0
0x1b53  call     instance class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::CreateXmlWriter(class [mscorlib]System.IO.Stream stream, bool disableUTF8Bom)
0x1b58  stloc.2
0x1b59  ldloc.2
0x1b5a  ldc.i4.1
0x1b5b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartDocument(bool)
0x1b60  ldarg.0
0x1b61  call     instance valuetype RenderingMode Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::get_Mode()
0x1b66  stloc.1
0x1b67  ldloc.1
0x1b68  switch   loc_1B7B, loc_1B86, loc_1B99
0x1b79  br.s     loc_1BA2
0x1b7b  ldarg.0
0x1b7c  ldloc.2
0x1b7d  ldarg.1
0x1b7e  ldarg.2
0x1b7f  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteAtomServiceDocument(class [System.Xml]System.Xml.XmlWriter xmlWriter, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report, class [System]System.Collections.Specialized.NameValueCollection reportServerParameters)
0x1b84  br.s     loc_1BA2
0x1b86  ldarg.0
0x1b87  ldloc.2
0x1b88  ldarg.1
0x1b89  ldarg.2
0x1b8a  ldarg.0
0x1b8b  ldfld    string[] Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::m_dataFeeds
0x1b90  ldc.i4.0
0x1b91  ldelem.ref
0x1b92  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteAtomDataFeed(class [System.Xml]System.Xml.XmlWriter xmlWriter, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report, class [System]System.Collections.Specialized.NameValueCollection reportServerParameters, string dataFeed)
0x1b97  br.s     loc_1BA2
0x1b99  ldarg.0
0x1b9a  ldloc.2
0x1b9b  ldarg.1
0x1b9c  ldarg.2
0x1b9d  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteCSDLMetadataDocument(class [System.Xml]System.Xml.XmlWriter xmlWriter, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report, class [System]System.Collections.Specialized.NameValueCollection reportServerParameters)
0x1ba2  ldloc.2
0x1ba3  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x1ba8  leave.s  loc_1BB4
0x1baa  ldloc.2
0x1bab  brfalse.s loc_1BB3
0x1bad  ldloc.2
0x1bae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1bb3  endfinally
0x1bb4  ldloc.0
0x1bb5  callvirt instance void [mscorlib]System.IO.Stream::Flush()
0x1bba  ret
```
