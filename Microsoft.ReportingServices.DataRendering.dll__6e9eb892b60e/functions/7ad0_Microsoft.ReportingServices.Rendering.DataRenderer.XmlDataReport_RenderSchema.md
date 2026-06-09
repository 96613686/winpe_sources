# Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::RenderSchema

- ea: `0x7ad0`
- end: `0x7b57`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::RenderSchema`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7880`

## callees

- `0x6c00`
- `0x6d00`
- `0x6d60`
- `0x6f70`
- `0x7ad0`
- `0x7b60`
- `0x7bb0`
- `0x7e80`
- `0x7eb0`
- `0x9f10`
- `0x9f20`
- `0xa6a0`
- `0xab30`

## pseudocode

```c

```

## disassembly

```asm
0x7ad0  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlTypeHandler::.ctor()
0x7ad5  stloc.0
0x7ad6  ldarg.0
0x7ad7  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_useFormattedValues
0x7adc  brtrue.s loc_7B1D
0x7ade  ldloc.0
0x7adf  ldloc.0
0x7ae0  ldloc.0
0x7ae1  ldnull
0x7ae2  ldc.i4.0
0x7ae3  ldc.i4.1
0x7ae4  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x7ae9  dup
0x7aea  ldarg.1
0x7aeb  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReport(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report)
0x7af0  callvirt instance class [mscorlib]System.Collections.IEnumerator Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::get_TopLevelDataRegionsOrMaps()
0x7af5  stloc.2
0x7af6  ldloc.0
0x7af7  ldloc.0
0x7af8  ldloc.0
0x7af9  ldnull
0x7afa  ldc.i4.1
0x7afb  ldc.i4.0
0x7afc  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x7b01  stloc.3
0x7b02  br.s     loc_7B15
0x7b04  ldloc.3
0x7b05  ldloc.2
0x7b06  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7b0b  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem
0x7b10  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkDataRegionOrMap(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem)
0x7b15  ldloc.2
0x7b16  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7b1b  brtrue.s loc_7B04
0x7b1d  ldarg.0
0x7b1e  ldarg.0
0x7b1f  ldarg.2
0x7b20  call     instance class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::CreateSchemaStream(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CreateAndRegisterStream createStream)
0x7b25  ldnull
0x7b26  call     instance class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::CreateXmlWriter(class [mscorlib]System.IO.Stream outputStream, class [System.Xml]System.Xml.XmlWriterSettings xws)
0x7b2b  ldarg.0
0x7b2c  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_schemaName
0x7b31  ldloc.0
0x7b32  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Rendering.DataRenderer.XmlTypeHandler::get_TextBoxTypes()
0x7b37  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::.ctor(class [System.Xml]System.Xml.XmlWriter xw, string schemaName, class [mscorlib]System.Collections.Hashtable textBoxTypes)
0x7b3c  stloc.1
0x7b3d  ldarg.1
0x7b3e  ldloc.1
0x7b3f  ldarg.0
0x7b40  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_useFormattedValues
0x7b45  ldc.i4.1
0x7b46  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::.ctor(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report aReport, class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor aXmlVisitor, bool aUseFormattedValues, bool aDoAttributesPass)
0x7b4b  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::ProcessReport()
0x7b50  ldloc.1
0x7b51  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::Flush()
0x7b56  ret
```
