# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteCSDLMetadataDocument

- ea: `0x1e90`
- end: `0x2022`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::WriteCSDLMetadataDocument`
- size: `402`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a90`
- `0x2110`

## callees

- `0x1170`
- `0x16c0`
- `0x19b0`
- `0x1e90`
- `0x2030`
- `0x2200`
- `0x22c0`
- `0x26b0`
- `0x29d0`
- `0x2d00`
- `0x2d10`
- `0x2d30`
- `0x2dd0`
- `0x2e00`
- `0x30b0`
- `0x31f0`
- `0x3520`
- `0x3550`
- `0x35d0`
- `0x3660`
- `0x37e0`
- `0x5740`
- `0x6c00`
- `0x6d00`
- `0x6d60`
- `0x6f70`

## pseudocode

```c

```

## disassembly

```asm
0x1e90  ldarg.1
0x1e91  ldarg.3
0x1e92  ldarg.2
0x1e93  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_Parameters()
0x1e98  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLDataVisitor::.ctor(class [System.Xml]System.Xml.XmlWriter xmlWriter, class [System]System.Collections.Specialized.NameValueCollection reportServerParameters, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterCollection reportParamters)
0x1e9d  stloc.0
0x1e9e  ldloc.0
0x1e9f  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::ClearColumnNames()
0x1ea4  ldloc.0
0x1ea5  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::ClearFeedLevelRowContent()
0x1eaa  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.NullHandler::.ctor()
0x1eaf  stloc.1
0x1eb0  ldloc.0
0x1eb1  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedTextBoxHandler::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor visitor)
0x1eb6  ldloc.1
0x1eb7  ldloc.1
0x1eb8  ldloc.1
0x1eb9  ldc.i4.0
0x1eba  ldc.i4.1
0x1ebb  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x1ec0  stloc.2
0x1ec1  ldloc.2
0x1ec2  ldarg.2
0x1ec3  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReport(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report)
0x1ec8  ldloc.2
0x1ec9  callvirt instance class [mscorlib]System.Collections.IEnumerator Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::get_TopLevelDataRegionsOrMaps()
0x1ece  stloc.3
0x1ecf  ldarg.1
0x1ed0  ldarg.3
0x1ed1  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLSchemaVisitor::.ctor(class [System.Xml]System.Xml.XmlWriter xmlWriter, class [System]System.Collections.Specialized.NameValueCollection reportServerParameters)
0x1ed6  stloc.s  4
0x1ed8  ldloc.s  4
0x1eda  ldarg.2
0x1edb  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLSchemaVisitor::CreateCSDLDocument(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report)
0x1ee0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0x1ee5  stloc.s  5
0x1ee7  ldloc.s  4
0x1ee9  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLSchemaVisitor::StartEntityContainer()
0x1eee  br.s     loc_1F22
0x1ef0  ldloc.s  4
0x1ef2  ldloc.s  5
0x1ef4  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandlerSql11::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.AtomSchemaVisitor visitor, class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> feedNames)
0x1ef9  stloc.s  6
0x1efb  ldloc.s  6
0x1efd  ldloc.s  6
0x1eff  ldloc.s  6
0x1f01  ldloc.s  6
0x1f03  ldc.i4.0
0x1f04  ldc.i4.0
0x1f05  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x1f0a  ldloc.3
0x1f0b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1f10  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem
0x1f15  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkDataRegionOrMap(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem)
0x1f1a  ldloc.s  6
0x1f1c  ldnull
0x1f1d  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::WriteCollection(class DynamicElement topLevelScope)
0x1f22  ldloc.3
0x1f23  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f28  brtrue.s loc_1EF0
0x1f2a  ldloc.s  4
0x1f2c  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLSchemaVisitor::EndEntityContainer()
0x1f31  ldloc.2
0x1f32  callvirt instance class [mscorlib]System.Collections.IEnumerator Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::get_TopLevelDataRegionsOrMaps()
0x1f37  stloc.3
0x1f38  br       loc_2016
0x1f3d  ldloc.3
0x1f3e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1f43  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem
0x1f48  stloc.s  7
0x1f4a  ldloc.s  4
0x1f4c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLSchemaVisitor::get_EntityTypes()
0x1f51  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Keys()
0x1f56  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, string>::GetEnumerator()
0x1f5b  stloc.s  8
0x1f5d  br       loc_1FFA
0x1f62  ldloca.s 8
0x1f64  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::get_Current()
0x1f69  stloc.s  9
0x1f6b  ldloc.s  7
0x1f6d  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_DefinitionPath()
0x1f72  ldloc.s  9
0x1f74  call     bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::IsOnDefinitionPath(string item, string path)
0x1f79  brfalse.s loc_1FFA
0x1f7b  ldloc.0
0x1f7c  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::CreateSyndicationFeed()
0x1f81  ldarg.0
0x1f82  ldloc.s  7
0x1f84  ldloc.s  9
0x1f86  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::GetStepsToDefinitonPath(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem, string definitionPath)
0x1f8b  stloc.s  0xA
0x1f8d  ldloc.0
0x1f8e  ldloc.s  0xA
0x1f90  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor visitor, class [mscorlib]System.Collections.Generic.List`1<string> definitionPathSteps)
0x1f95  stloc.s  0xB
0x1f97  ldloc.s  0xB
0x1f99  ldloc.s  0xB
0x1f9b  ldloc.s  0xB
0x1f9d  ldloc.s  0xB
0x1f9f  ldc.i4.0
0x1fa0  ldc.i4.0
0x1fa1  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x1fa6  ldloc.s  7
0x1fa8  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkDataRegionOrMap(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem)
0x1fad  ldarg.0
0x1fae  ldloc.s  7
0x1fb0  ldloc.s  0xA
0x1fb2  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::ResolveDataTypes(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem, class [mscorlib]System.Collections.Generic.List`1<string> definitionPathSteps)
0x1fb7  stloc.s  0xC
0x1fb9  ldloc.0
0x1fba  ldloc.s  0xC
0x1fbc  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::SetResolvedEdmTypes(class [mscorlib]System.Collections.Generic.List`1<string> resolvedEdmTypes)
0x1fc1  ldloc.0
0x1fc2  ldloc.s  0xA
0x1fc4  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor visitor, class [mscorlib]System.Collections.Generic.List`1<string> definitionPathSteps)
0x1fc9  stloc.s  0xD
0x1fcb  ldloc.s  0xD
0x1fcd  ldloc.s  0xD
0x1fcf  ldloc.s  0xD
0x1fd1  ldloc.s  0xD
0x1fd3  ldc.i4.1
0x1fd4  ldc.i4.0
0x1fd5  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::.ctor(class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler reportHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.IOutputRowHandler outputRowHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.ITablixHandler tablixHandler, class Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase dvHandler, bool instanceWalk, bool walkTopLevelOnly)
0x1fda  stloc.s  0xE
0x1fdc  ldloc.0
0x1fdd  ldloc.s  0xE
0x1fdf  ldloc.s  7
0x1fe1  ldloc.s  4
0x1fe3  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLSchemaVisitor::get_EntityTypes()
0x1fe8  ldloc.s  9
0x1fea  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x1fef  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteDataRegionFeed(class Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker dataRegionWalker, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem, string feedName)
0x1ff4  ldloc.0
0x1ff5  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::ResetColumnNames()
0x1ffa  ldloca.s 8
0x1ffc  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::MoveNext()
0x2001  brtrue   loc_1F62
0x2006  leave.s  loc_2016
0x2008  ldloca.s 8
0x200a  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>
0x2010  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2015  endfinally
0x2016  ldloc.3
0x2017  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x201c  brtrue   loc_1F3D
0x2021  ret
```
