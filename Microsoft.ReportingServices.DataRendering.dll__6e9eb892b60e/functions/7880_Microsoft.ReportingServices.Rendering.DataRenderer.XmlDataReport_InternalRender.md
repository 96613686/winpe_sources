# Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::InternalRender

- ea: `0x7880`
- end: `0x78e6`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::InternalRender`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7880`
- `0x78f0`
- `0x7ad0`
- `0x7c60`
- `0x7c80`

## pseudocode

```c

```

## disassembly

```asm
0x7880  ldarg.0
0x7881  ldarg.1
0x7882  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::ReadReportAttributes(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report)
0x7887  ldarg.0
0x7888  ldarg.3
0x7889  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::ParseDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo)
0x788e  ldarg.0
0x788f  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_innerXSLT
0x7894  brtrue.s loc_78A6
0x7896  ldarg.0
0x7897  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_outerXSLT
0x789c  brtrue.s loc_78A6
0x789e  ldarg.0
0x789f  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_noNamespace
0x78a4  brfalse.s loc_78AD
0x78a6  ldarg.0
0x78a7  ldc.i4.1
0x78a8  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_noSchema
0x78ad  ldarg.0
0x78ae  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_schemaName
0x78b3  brtrue.s loc_78CF
0x78b5  ldarg.0
0x78b6  ldarg.1
0x78b7  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_Name()
0x78bc  dup
0x78bd  brtrue.s loc_78C5
0x78bf  pop
0x78c0  ldsfld   string [mscorlib]System.String::Empty
0x78c5  call     string [System.Xml]System.Xml.XmlConvert::EncodeLocalName(string)
0x78ca  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_schemaName
0x78cf  brfalse.s loc_78DC
0x78d1  ldarg.0
0x78d2  ldarg.1
0x78d3  ldarg.s  5
0x78d5  ldarg.2
0x78d6  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::RenderData(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report, class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CreateAndRegisterStream createStream, class [System]System.Collections.Specialized.NameValueCollection reportServerParameters)
0x78db  ret
0x78dc  ldarg.0
0x78dd  ldarg.1
0x78de  ldarg.s  5
0x78e0  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::RenderSchema(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report, class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CreateAndRegisterStream createStream)
0x78e5  ret
```
