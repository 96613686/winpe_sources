# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor

- ea: `0x6c00`
- end: `0x6c86`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor`
- size: `134`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1cf0`
- `0x1d70`
- `0x1e90`
- `0x2030`
- `0x21e0`
- `0x2200`
- `0x4a00`
- `0x5aa0`
- `0x7ad0`

## callees

- `0x6c00`

## pseudocode

```c

```

## disassembly

```asm
0x6c00  ldarg.0
0x6c01  ldc.i4.1
0x6c02  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_walkTopLevelOnly
0x6c07  ldarg.0
0x6c08  ldc.i4.1
0x6c09  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_firstInstancePass
0x6c0e  ldarg.0
0x6c0f  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x6c14  stfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_dataRegionsOrMaps
0x6c19  ldarg.0
0x6c1a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::.ctor()
0x6c1f  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_activeDefinitionPaths
0x6c24  ldarg.0
0x6c25  call     instance void [mscorlib]System.Object::.ctor()
0x6c2a  ldarg.0
0x6c2b  ldarg.1
0x6c2c  stfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x6c31  ldarg.0
0x6c32  ldarg.3
0x6c33  stfld    class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_tablixHandler
0x6c38  ldarg.0
0x6c39  ldarg.2
0x6c3a  stfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_outputRowHandler
0x6c3f  ldarg.0
0x6c40  ldarg.s  5
0x6c42  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_instanceWalk
0x6c47  ldarg.0
0x6c48  ldarg.s  6
0x6c4a  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_walkTopLevelOnly
0x6c4f  ldarg.0
0x6c50  ldarg.s  4
0x6c52  stfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IChartHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_chartHandler
0x6c57  ldarg.0
0x6c58  ldarg.s  4
0x6c5a  stfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IGaugePanelHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_gaugePanelHandler
0x6c5f  ldarg.0
0x6c60  ldarg.s  4
0x6c62  stfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IMapHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_mapHandler
0x6c67  ldarg.1
0x6c68  isinst   Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase
0x6c6d  brfalse.s loc_6C85
0x6c6f  ldarg.0
0x6c70  ldc.i4.1
0x6c71  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_atomRendererWalk
0x6c76  ldarg.1
0x6c77  isinst   Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler
0x6c7c  brfalse.s loc_6C85
0x6c7e  ldarg.0
0x6c7f  ldc.i4.1
0x6c80  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_atomHeaderInstanceWalk
0x6c85  ret
```
