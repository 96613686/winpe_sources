# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkMap

- ea: `0x7170`
- end: `0x725d`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkMap`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x7390`

## callees

- `0x5980`
- `0x5990`
- `0x6400`
- `0x7170`
- `0xc9b0`
- `0xcb10`
- `0xcbb0`
- `0xcc30`

## pseudocode

```c

```

## disassembly

```asm
0x7170  ldarg.1
0x7171  brfalse.s loc_717B
0x7173  ldarg.0
0x7174  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IMapHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_mapHandler
0x7179  brtrue.s loc_717C
0x717b  ret
0x717c  ldc.i4.0
0x717d  stloc.0
0x717e  ldarg.0
0x717f  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_atomRendererWalk
0x7184  brfalse.s loc_71B5
0x7186  ldarg.0
0x7187  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_firstInstancePass
0x718c  brfalse.s loc_719D
0x718e  ldarg.1
0x718f  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementOutput()
0x7194  ldc.i4.1
0x7195  ceq
0x7197  ldc.i4.0
0x7198  ceq
0x719a  stloc.0
0x719b  br.s     loc_71B5
0x719d  ldarg.2
0x719e  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::get_IsDynamic()
0x71a3  brtrue.s loc_71B3
0x71a5  ldarg.1
0x71a6  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementOutput()
0x71ab  ldc.i4.1
0x71ac  ceq
0x71ae  ldc.i4.0
0x71af  ceq
0x71b1  br.s     loc_71B4
0x71b3  ldloc.0
0x71b4  stloc.0
0x71b5  ldarg.0
0x71b6  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IMapHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_mapHandler
0x71bb  ldarg.1
0x71bc  ldarg.3
0x71bd  ldloca.s 0
0x71bf  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IMapHandler::OnMapBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map map, bool outputMap, bool& walkMap)
0x71c4  ldloc.0
0x71c5  brfalse  loc_725C
0x71ca  ldarg.1
0x71cb  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapLayerCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map::get_MapLayers()
0x71d0  brfalse.s loc_7250
0x71d2  ldarg.1
0x71d3  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapLayerCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map::get_MapLayers()
0x71d8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapLayer>::GetEnumerator()
0x71dd  stloc.1
0x71de  br.s     loc_723C
0x71e0  ldloc.1
0x71e1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapLayer>::get_Current()
0x71e6  stloc.2
0x71e7  ldloc.2
0x71e8  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapPolygonLayer
0x71ed  brfalse.s loc_7204
0x71ef  ldloc.2
0x71f0  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapPolygonLayer
0x71f5  ldarg.0
0x71f6  newobj   instance void MapPolygonLayerWalker::.ctor(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapPolygonLayer layer, class Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker reportWalker)
0x71fb  ldarg.2
0x71fc  ldarg.3
0x71fd  call     instance void MapVectorLayerWalker::WalkLayer(class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState mapState, bool outputMapData)
0x7202  br.s     loc_723C
0x7204  ldloc.2
0x7205  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapPointLayer
0x720a  brfalse.s loc_7221
0x720c  ldloc.2
0x720d  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapPointLayer
0x7212  ldarg.0
0x7213  newobj   instance void MapPointLayerWalker::.ctor(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapPointLayer layer, class Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker reportWalker)
0x7218  ldarg.2
0x7219  ldarg.3
0x721a  call     instance void MapVectorLayerWalker::WalkLayer(class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState mapState, bool outputMapData)
0x721f  br.s     loc_723C
0x7221  ldloc.2
0x7222  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapLineLayer
0x7227  brfalse.s loc_723C
0x7229  ldloc.2
0x722a  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapLineLayer
0x722f  ldarg.0
0x7230  newobj   instance void MapLineLayerWalker::.ctor(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapLineLayer layer, class Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker reportWalker)
0x7235  ldarg.2
0x7236  ldarg.3
0x7237  call     instance void MapVectorLayerWalker::WalkLayer(class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState mapState, bool outputMapData)
0x723c  ldloc.1
0x723d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7242  brtrue.s loc_71E0
0x7244  leave.s  loc_7250
0x7246  ldloc.1
0x7247  brfalse.s loc_724F
0x7249  ldloc.1
0x724a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x724f  endfinally
0x7250  ldarg.0
0x7251  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IMapHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_mapHandler
0x7256  ldarg.1
0x7257  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IMapHandler::OnMapEnd(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map map)
0x725c  ret
```
