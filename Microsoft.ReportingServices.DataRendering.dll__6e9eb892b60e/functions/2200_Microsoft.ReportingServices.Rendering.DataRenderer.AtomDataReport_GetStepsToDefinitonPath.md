# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::GetStepsToDefinitonPath

- ea: `0x2200`
- end: `0x2237`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::GetStepsToDefinitonPath`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d70`
- `0x1e90`

## callees

- `0x2240`
- `0x2380`
- `0x27b0`
- `0x2bd0`
- `0x6c00`
- `0x6d60`

## pseudocode

```c

```

## disassembly

```asm
0x2200  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x2205  stloc.0
0x2206  ldnull
0x2207  ldnull
0x2208  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentVisitor::.ctor(class [System.Xml]System.Xml.XmlWriter xmlWriter, class [System]System.Collections.Specialized.NameValueCollection reportServerParameters)
0x220d  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.AtomSchemaVisitor visitor)
0x2212  stloc.1
0x2213  ldloc.1
0x2214  ldloc.1
0x2215  ldloc.1
0x2216  ldloc.1
0x2217  ldc.i4.0
0x2218  ldc.i4.0
0x2219  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x221e  ldarg.1
0x221f  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkDataRegionOrMap(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem)
0x2224  ldloc.1
0x2225  callvirt instance class DynamicElement Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::GetTopLevelDynamicElement()
0x222a  stloc.2
0x222b  ldarg.0
0x222c  ldloc.2
0x222d  ldarg.2
0x222e  ldloc.0
0x222f  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::TraverseStepsToDefinitionPath(class DynamicElement dynamicElement, string definitionPath, class [mscorlib]System.Collections.Generic.List`1<string> steps)
0x2234  pop
0x2235  ldloc.0
0x2236  ret
```
