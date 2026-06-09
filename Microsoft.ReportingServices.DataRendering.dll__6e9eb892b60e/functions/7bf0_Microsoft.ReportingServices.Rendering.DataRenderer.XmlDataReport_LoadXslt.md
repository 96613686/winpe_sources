# Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::LoadXslt

- ea: `0x7bf0`
- end: `0x7c51`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::LoadXslt`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x78f0`

## callees

- `0x120`
- `0x7840`
- `0x7bf0`

## pseudocode

```c

```

## disassembly

```asm
0x7bf0  ldnull
0x7bf1  stloc.0
0x7bf2  ldc.i4.0
0x7bf3  stloc.2
0x7bf4  ldarg.2
0x7bf5  ldc.i4.1
0x7bf6  ldloca.s 2
0x7bf8  call     bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RSPathUtil::IsReportServerPathOrUrl(string, bool, bool&)
0x7bfd  ldloc.2
0x7bfe  and
0x7bff  brfalse.s loc_7C30
0x7c01  ldarg.1
0x7c02  ldarg.2
0x7c03  ldloca.s 0
0x7c05  ldloca.s 1
0x7c07  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::GetResource(string, unsigned int8[]&, string&)
0x7c0c  brfalse.s loc_7C30
0x7c0e  ldloc.0
0x7c0f  brfalse.s loc_7C30
0x7c11  ldloc.0
0x7c12  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x7c17  call     class [System.Xml]System.Xml.XmlTextReader [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeCreateXmlTextReader(class [mscorlib]System.IO.Stream)
0x7c1c  stloc.3
0x7c1d  ldarg.3
0x7c1e  ldloc.3
0x7c1f  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Load(class [System.Xml]System.Xml.XmlReader)
0x7c24  leave.s  loc_7C30
0x7c26  ldloc.3
0x7c27  brfalse.s loc_7C2F
0x7c29  ldloc.3
0x7c2a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7c2f  endfinally
0x7c30  ldloc.0
0x7c31  brtrue.s loc_7C3E
0x7c33  call     string Microsoft.ReportingServices.DataRendering.StringResources::get_rrBadXsltPath()
0x7c38  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(string)
0x7c3d  throw
0x7c3e  leave.s  loc_7C50
0x7c40  stloc.s  4
0x7c42  ldarg.2
0x7c43  call     string Microsoft.ReportingServices.Rendering.DataRenderer.StringResourcesWrapper::rrCanNotLoadXSLT(string path)
0x7c48  ldloc.s  4
0x7c4a  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(string, class [mscorlib]System.Exception)
0x7c4f  throw
0x7c50  ret
```
