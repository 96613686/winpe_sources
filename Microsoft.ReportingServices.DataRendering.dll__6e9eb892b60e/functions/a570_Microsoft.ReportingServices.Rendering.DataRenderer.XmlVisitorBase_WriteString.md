# Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteString

- ea: `0xa570`
- end: `0xa5a2`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteString`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb340`

## callees

- `0xa460`
- `0xa570`

## string_xrefs

- `0xa57e`: `The xml writer should not be null`

## pseudocode

```c

```

## disassembly

```asm
0xa570  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0xa575  ldarg.0
0xa576  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xa57b  ldnull
0xa57c  cgt.un
0xa57e  ldstr    aTheXmlWriterSh// "The xml writer should not be null"
0xa583  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0xa588  ldarg.0
0xa589  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xa58e  ldarg.1
0xa58f  call     string Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::FilterInvalidXMLCharacters(string value)
0xa594  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0xa599  leave.s  loc_A5A1
0xa59b  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(class [mscorlib]System.Exception)
0xa5a0  throw
0xa5a1  ret
```
