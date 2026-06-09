# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::GetDynamicElementTree

- ea: `0x21e0`
- end: `0x2200`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::GetDynamicElementTree`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d70`

## callees

- `0x23e0`
- `0x29d0`
- `0x6c00`
- `0x6f70`

## pseudocode

```c

```

## disassembly

```asm
0x21e0  ldnull
0x21e1  ldnull
0x21e2  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandlerSql11::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.AtomSchemaVisitor visitor, class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> feedNames)
0x21e7  stloc.0
0x21e8  ldloc.0
0x21e9  ldloc.0
0x21ea  ldloc.0
0x21eb  ldloc.0
0x21ec  ldc.i4.0
0x21ed  ldc.i4.0
0x21ee  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x21f3  ldarg.0
0x21f4  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReport(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report)
0x21f9  ldloc.0
0x21fa  callvirt instance class DynamicElement Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::get_DynamicElementRoot()
0x21ff  ret
```
