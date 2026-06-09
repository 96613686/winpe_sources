# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::ResolveDataTypes

- ea: `0x2030`
- end: `0x205d`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::ResolveDataTypes`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d70`
- `0x1e90`

## callees

- `0x1170`
- `0x30a0`
- `0x31f0`
- `0x39b0`
- `0x39c0`
- `0x6c00`

## pseudocode

```c

```

## disassembly

```asm
0x2030  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataTypeVisitor::.ctor()
0x2035  dup
0x2036  ldarg.2
0x2037  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor visitor, class [mscorlib]System.Collections.Generic.List`1<string> definitionPathSteps)
0x203c  stloc.0
0x203d  ldloc.0
0x203e  ldloc.0
0x203f  ldloc.0
0x2040  ldloc.0
0x2041  ldc.i4.1
0x2042  ldc.i4.0
0x2043  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x2048  stloc.1
0x2049  dup
0x204a  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::CreateSyndicationFeed()
0x204f  dup
0x2050  ldloc.1
0x2051  ldarg.1
0x2052  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteDataRegionFeed(class Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker dataRegionWalker, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem)
0x2057  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataTypeVisitor::get_ColumnEdmTypes()
0x205c  ret
```
