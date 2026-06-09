# Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString

- ea: `0xa4f0`
- end: `0xa523`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString`
- size: `51`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xa6a0`
- `0xab80`
- `0xac50`
- `0xadf0`
- `0xb380`

## callees

- `0xa460`
- `0xa4f0`

## string_xrefs

- `0xa4fe`: `The xml writer should not be null`

## pseudocode

```c

```

## disassembly

```asm
0xa4f0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0xa4f5  ldarg.0
0xa4f6  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xa4fb  ldnull
0xa4fc  cgt.un
0xa4fe  ldstr    aTheXmlWriterSh// "The xml writer should not be null"
0xa503  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0xa508  ldarg.0
0xa509  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xa50e  ldarg.1
0xa50f  ldarg.2
0xa510  call     string Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::FilterInvalidXMLCharacters(string value)
0xa515  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xa51a  leave.s  loc_A522
0xa51c  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(class [mscorlib]System.Exception)
0xa521  throw
0xa522  ret
```
