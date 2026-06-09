# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablix

- ea: `0x82d0`
- end: `0x83a2`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablix`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x8130`

## callees

- `0x82d0`
- `0x83d0`
- `0x8460`
- `0x9f90`
- `0xa020`
- `0xa090`
- `0xa0f0`

## pseudocode

```c

```

## disassembly

```asm
0x82d0  ldarg.0
0x82d1  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentRow
0x82d6  stloc.0
0x82d7  ldarg.1
0x82d8  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementOutput()
0x82dd  ldc.i4.1
0x82de  bne.un.s loc_82E1
0x82e0  ret
0x82e1  ldarg.0
0x82e2  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x82e7  ldarg.1
0x82e8  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementName()
0x82ed  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x82f2  stloc.1
0x82f3  ldloc.1
0x82f4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x82f9  brfalse.s loc_8307
0x82fb  ldarg.0
0x82fc  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8301  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultTablixTag()
0x8306  stloc.1
0x8307  ldarg.0
0x8308  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x830d  ldloc.1
0x830e  ldarg.2
0x830f  ldc.i4.0
0x8310  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartDataRegion(string name, bool firstInstance, bool optional)
0x8315  ldc.i4.0
0x8316  stloc.2
0x8317  ldarg.1
0x8318  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCorner [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix::get_Corner()
0x831d  brfalse.s loc_8333
0x831f  ldarg.0
0x8320  ldarg.1
0x8321  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCorner [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix::get_Corner()
0x8326  ldarg.0
0x8327  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_DoAttributesPass
0x832c  ldarg.2
0x832d  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixCorner(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCorner aTablixCorner, bool aAttributesOnly, bool firstInstance)
0x8332  stloc.2
0x8333  ldc.i4.0
0x8334  stloc.3
0x8335  ldarg.1
0x8336  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHierarchy [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix::get_RowHierarchy()
0x833b  brfalse.s loc_8364
0x833d  ldarg.1
0x833e  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHierarchy [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix::get_RowHierarchy()
0x8343  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHierarchy::get_MemberCollection()
0x8348  brfalse.s loc_8364
0x834a  ldarg.0
0x834b  ldarg.1
0x834c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHierarchy [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix::get_RowHierarchy()
0x8351  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHierarchy::get_MemberCollection()
0x8356  ldarg.1
0x8357  ldarg.0
0x8358  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_DoAttributesPass
0x835d  ldarg.2
0x835e  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixMemberCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection aMemberCollection, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix, bool aAttributesOnly, bool firstInstance)
0x8363  stloc.3
0x8364  ldloc.2
0x8365  brfalse.s loc_8376
0x8367  ldarg.0
0x8368  ldarg.1
0x8369  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCorner [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix::get_Corner()
0x836e  ldc.i4.0
0x836f  ldarg.2
0x8370  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixCorner(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCorner aTablixCorner, bool aAttributesOnly, bool firstInstance)
0x8375  pop
0x8376  ldloc.3
0x8377  brfalse.s loc_838E
0x8379  ldarg.0
0x837a  ldarg.1
0x837b  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHierarchy [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix::get_RowHierarchy()
0x8380  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHierarchy::get_MemberCollection()
0x8385  ldarg.1
0x8386  ldc.i4.0
0x8387  ldarg.2
0x8388  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixMemberCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection aMemberCollection, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix, bool aAttributesOnly, bool firstInstance)
0x838d  pop
0x838e  ldarg.0
0x838f  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8394  ldarg.2
0x8395  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x839a  ldarg.0
0x839b  ldloc.0
0x839c  stfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentRow
0x83a1  ret
```
