# Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString_0

- ea: `0xa530`
- end: `0xa566`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString_0`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb240`

## callees

- `0xa460`
- `0xa530`

## string_xrefs

- `0xa53e`: `The xml writer should not be null`

## pseudocode

```c

```

## disassembly

```asm
0xa530  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0xa535  ldarg.0
0xa536  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xa53b  ldnull
0xa53c  cgt.un
0xa53e  ldstr    aTheXmlWriterSh// "The xml writer should not be null"
0xa543  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0xa548  ldarg.0
0xa549  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xa54e  ldarg.1
0xa54f  ldarg.2
0xa550  ldarg.3
0xa551  ldarg.s  4
0xa553  call     string Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::FilterInvalidXMLCharacters(string value)
0xa558  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0xa55d  leave.s  loc_A565
0xa55f  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(class [mscorlib]System.Exception)
0xa564  throw
0xa565  ret
```
