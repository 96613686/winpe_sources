# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkMap

- ea: `0x9b70`
- end: `0x9c5f`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkMap`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x8130`

## callees

- `0x9b70`
- `0x9f90`
- `0xa020`
- `0xa090`
- `0xcd20`
- `0xd030`
- `0xd0d0`
- `0xd150`

## pseudocode

```c

```

## disassembly

```asm
0x9b70  ldarg.1
0x9b71  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementOutput()
0x9b76  ldc.i4.1
0x9b77  bne.un.s loc_9B7A
0x9b79  ret
0x9b7a  ldarg.0
0x9b7b  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9b80  ldarg.0
0x9b81  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9b86  ldarg.1
0x9b87  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementName()
0x9b8c  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x9b91  ldarg.2
0x9b92  ldc.i4.0
0x9b93  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartDataRegion(string name, bool firstInstance, bool optional)
0x9b98  ldarg.1
0x9b99  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapLayerCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map::get_MapLayers()
0x9b9e  brtrue.s loc_9BA1
0x9ba0  ret
0x9ba1  ldarg.1
0x9ba2  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapLayerCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Map::get_MapLayers()
0x9ba7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapLayer>::GetEnumerator()
0x9bac  stloc.0
0x9bad  br       loc_9C3B
0x9bb2  ldloc.0
0x9bb3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapLayer>::get_Current()
0x9bb8  stloc.1
0x9bb9  ldloc.1
0x9bba  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapPolygonLayer
0x9bbf  brfalse.s loc_9BE5
0x9bc1  ldloc.1
0x9bc2  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapPolygonLayer
0x9bc7  ldarg.0
0x9bc8  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9bcd  ldarg.0
0x9bce  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentReport
0x9bd3  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report/DataElementStyles [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_DataElementStyle()
0x9bd8  newobj   instance void MapPolygonLayerWalker::.ctor(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapPolygonLayer layer, class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor visitor, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report/DataElementStyles dataElementStyle)
0x9bdd  ldarg.2
0x9bde  call     instance void MapVectorLayerWalker::Walk(bool firstInstance)
0x9be3  br.s     loc_9C3B
0x9be5  ldloc.1
0x9be6  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapPointLayer
0x9beb  brfalse.s loc_9C11
0x9bed  ldloc.1
0x9bee  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapPointLayer
0x9bf3  ldarg.0
0x9bf4  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9bf9  ldarg.0
0x9bfa  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentReport
0x9bff  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report/DataElementStyles [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_DataElementStyle()
0x9c04  newobj   instance void MapPointLayerWalker::.ctor(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapPointLayer layer, class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor visitor, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report/DataElementStyles dataElementStyle)
0x9c09  ldarg.2
0x9c0a  call     instance void MapVectorLayerWalker::Walk(bool firstInstance)
0x9c0f  br.s     loc_9C3B
0x9c11  ldloc.1
0x9c12  isinst   [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapLineLayer
0x9c17  brfalse.s loc_9C3B
0x9c19  ldloc.1
0x9c1a  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapLineLayer
0x9c1f  ldarg.0
0x9c20  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9c25  ldarg.0
0x9c26  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentReport
0x9c2b  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report/DataElementStyles [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_DataElementStyle()
0x9c30  newobj   instance void MapLineLayerWalker::.ctor(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.MapLineLayer layer, class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor visitor, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report/DataElementStyles dataElementStyle)
0x9c35  ldarg.2
0x9c36  call     instance void MapVectorLayerWalker::Walk(bool firstInstance)
0x9c3b  ldloc.0
0x9c3c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9c41  brtrue   loc_9BB2
0x9c46  leave.s  loc_9C52
0x9c48  ldloc.0
0x9c49  brfalse.s loc_9C51
0x9c4b  ldloc.0
0x9c4c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9c51  endfinally
0x9c52  ldarg.0
0x9c53  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9c58  ldarg.2
0x9c59  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x9c5e  ret
```
