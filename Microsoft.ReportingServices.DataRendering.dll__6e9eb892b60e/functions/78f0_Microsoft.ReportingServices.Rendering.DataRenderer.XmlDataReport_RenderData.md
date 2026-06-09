# Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::RenderData

- ea: `0x78f0`
- end: `0x7a5a`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::RenderData`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7880`

## callees

- `0x140`
- `0x78f0`
- `0x7a60`
- `0x7b60`
- `0x7b90`
- `0x7bd0`
- `0x7bf0`

## string_xrefs

- `0x797c`: `temp1Stream`
- `0x79f7`: `temp2Stream`

## pseudocode

```c

```

## disassembly

```asm
0x78f0  ldnull
0x78f1  stloc.0
0x78f2  ldarg.0
0x78f3  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_innerXSLT
0x78f8  brtrue.s loc_7921
0x78fa  ldarg.0
0x78fb  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_outerXSLT
0x7900  brtrue.s loc_7921
0x7902  ldarg.0
0x7903  ldarg.0
0x7904  ldarg.1
0x7905  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_Name()
0x790a  ldarg.2
0x790b  call     instance class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::CreateDataStream(string aStreamName, class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CreateAndRegisterStream createStream)
0x7910  ldnull
0x7911  call     instance class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::CreateXmlWriter(class [mscorlib]System.IO.Stream outputStream, class [System.Xml]System.Xml.XmlWriterSettings xws)
0x7916  stloc.0
0x7917  ldarg.0
0x7918  ldarg.1
0x7919  ldarg.3
0x791a  ldloc.0
0x791b  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::RenderReportData(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report, class [System]System.Collections.Specialized.NameValueCollection reportServerParameters, class [System.Xml]System.Xml.XmlWriter outputStream)
0x7920  ret
0x7921  ldnull
0x7922  stloc.1
0x7923  ldnull
0x7924  stloc.2
0x7925  ldarg.0
0x7926  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_innerXSLT
0x792b  brfalse.s loc_7941
0x792d  newobj   instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::.ctor()
0x7932  stloc.1
0x7933  ldarg.0
0x7934  ldarg.1
0x7935  ldarg.0
0x7936  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_innerXSLT
0x793b  ldloc.1
0x793c  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::LoadXslt(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report, string xsltPath, class [System.Xml]System.Xml.Xsl.XslCompiledTransform xslt)
0x7941  ldarg.0
0x7942  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_outerXSLT
0x7947  brfalse.s loc_7976
0x7949  ldloc.1
0x794a  brtrue.s loc_7962
0x794c  newobj   instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::.ctor()
0x7951  stloc.1
0x7952  ldarg.0
0x7953  ldarg.1
0x7954  ldarg.0
0x7955  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_outerXSLT
0x795a  ldloc.1
0x795b  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::LoadXslt(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report, string xsltPath, class [System.Xml]System.Xml.Xsl.XslCompiledTransform xslt)
0x7960  br.s     loc_7976
0x7962  newobj   instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::.ctor()
0x7967  stloc.2
0x7968  ldarg.0
0x7969  ldarg.1
0x796a  ldarg.0
0x796b  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_outerXSLT
0x7970  ldloc.2
0x7971  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::LoadXslt(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report, string xsltPath, class [System.Xml]System.Xml.Xsl.XslCompiledTransform xslt)
0x7976  ldnull
0x7977  stloc.3
0x7978  ldnull
0x7979  stloc.s  4
0x797b  ldarg.0
0x797c  ldstr    aTemp1stream// "temp1Stream"
0x7981  ldarg.2
0x7982  call     instance class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::CreateTempStream(string name, class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CreateAndRegisterStream createStream)
0x7987  stloc.3
0x7988  ldarg.0
0x7989  ldarg.1
0x798a  ldarg.3
0x798b  ldarg.0
0x798c  ldloc.3
0x798d  ldnull
0x798e  call     instance class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::CreateXmlWriter(class [mscorlib]System.IO.Stream outputStream, class [System.Xml]System.Xml.XmlWriterSettings xws)
0x7993  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::RenderReportData(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report, class [System]System.Collections.Specialized.NameValueCollection reportServerParameters, class [System.Xml]System.Xml.XmlWriter outputStream)
0x7998  ldloc.3
0x7999  ldc.i4.0
0x799a  conv.i8
0x799b  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x79a0  ldloc.2
0x79a1  brtrue.s loc_79DC
0x79a3  ldarg.0
0x79a4  ldarg.0
0x79a5  ldarg.1
0x79a6  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_Name()
0x79ab  ldarg.2
0x79ac  call     instance class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::CreateDataStream(string aStreamName, class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CreateAndRegisterStream createStream)
0x79b1  ldloc.1
0x79b2  callvirt instance class [System.Xml]System.Xml.XmlWriterSettings [System.Xml]System.Xml.Xsl.XslCompiledTransform::get_OutputSettings()
0x79b7  call     instance class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::CreateXmlWriter(class [mscorlib]System.IO.Stream outputStream, class [System.Xml]System.Xml.XmlWriterSettings xws)
0x79bc  stloc.0
0x79bd  ldloc.1
0x79be  ldloc.3
0x79bf  call     class [System.Xml]System.Xml.XmlTextReader [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeCreateXmlTextReader(class [mscorlib]System.IO.Stream)
0x79c4  ldnull
0x79c5  ldloc.0
0x79c6  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Transform(class [System.Xml]System.Xml.XmlReader, class [System.Xml]System.Xml.Xsl.XsltArgumentList, class [System.Xml]System.Xml.XmlWriter)
0x79cb  leave.s  loc_7A3C
0x79cd  stloc.s  5
0x79cf  call     string Microsoft.ReportingServices.DataRendering.StringResources::get_rrBadXsltTransformation()
0x79d4  ldloc.s  5
0x79d6  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(string, class [mscorlib]System.Exception)
0x79db  throw
0x79dc  ldarg.0
0x79dd  ldarg.0
0x79de  ldarg.1
0x79df  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_Name()
0x79e4  ldarg.2
0x79e5  call     instance class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::CreateDataStream(string aStreamName, class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CreateAndRegisterStream createStream)
0x79ea  ldloc.2
0x79eb  callvirt instance class [System.Xml]System.Xml.XmlWriterSettings [System.Xml]System.Xml.Xsl.XslCompiledTransform::get_OutputSettings()
0x79f0  call     instance class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::CreateXmlWriter(class [mscorlib]System.IO.Stream outputStream, class [System.Xml]System.Xml.XmlWriterSettings xws)
0x79f5  stloc.0
0x79f6  ldarg.0
0x79f7  ldstr    aTemp2stream// "temp2Stream"
0x79fc  ldarg.2
0x79fd  call     instance class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::CreateTempStream(string name, class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CreateAndRegisterStream createStream)
0x7a02  stloc.s  4
0x7a04  ldloc.1
0x7a05  ldloc.3
0x7a06  call     class [System.Xml]System.Xml.XmlTextReader [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeCreateXmlTextReader(class [mscorlib]System.IO.Stream)
0x7a0b  ldnull
0x7a0c  ldloc.s  4
0x7a0e  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Transform(class [System.Xml]System.Xml.XmlReader, class [System.Xml]System.Xml.Xsl.XsltArgumentList, class [mscorlib]System.IO.Stream)
0x7a13  ldloc.s  4
0x7a15  ldc.i4.0
0x7a16  conv.i8
0x7a17  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x7a1c  ldloc.2
0x7a1d  ldloc.s  4
0x7a1f  call     class [System.Xml]System.Xml.XmlTextReader [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeCreateXmlTextReader(class [mscorlib]System.IO.Stream)
0x7a24  ldnull
0x7a25  ldloc.0
0x7a26  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Transform(class [System.Xml]System.Xml.XmlReader, class [System.Xml]System.Xml.Xsl.XsltArgumentList, class [System.Xml]System.Xml.XmlWriter)
0x7a2b  leave.s  loc_7A3C
0x7a2d  stloc.s  6
0x7a2f  call     string Microsoft.ReportingServices.DataRendering.StringResources::get_rrBadXsltTransformation()
0x7a34  ldloc.s  6
0x7a36  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(string, class [mscorlib]System.Exception)
0x7a3b  throw
0x7a3c  ldloc.0
0x7a3d  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x7a42  leave.s  loc_7A59
0x7a44  ldloc.3
0x7a45  brfalse.s loc_7A4D
0x7a47  ldloc.3
0x7a48  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x7a4d  ldloc.s  4
0x7a4f  brfalse.s loc_7A58
0x7a51  ldloc.s  4
0x7a53  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x7a58  endfinally
0x7a59  ret
```
