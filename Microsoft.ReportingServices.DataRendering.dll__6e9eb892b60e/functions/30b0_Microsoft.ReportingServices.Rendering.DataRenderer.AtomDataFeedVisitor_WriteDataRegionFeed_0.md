# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteDataRegionFeed_0

- ea: `0x30b0`
- end: `0x30e5`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteDataRegionFeed_0`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e90`
- `0x30a0`

## callees

- `0x30b0`
- `0x30f0`
- `0x3110`
- `0x3290`

## pseudocode

```c

```

## disassembly

```asm
0x30b0  ldarg.0
0x30b1  ldarg.1
0x30b2  stfld    class Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_dataRegionWalker
0x30b7  ldarg.0
0x30b8  ldarg.2
0x30b9  stfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_reportItem
0x30be  ldarg.0
0x30bf  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_hasDuplicateColumnNames
0x30c4  brfalse.s loc_30CC
0x30c6  ldarg.0
0x30c7  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::ResolveDuplicateColumnNames()
0x30cc  ldarg.0
0x30cd  ldfld    class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationFeed Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_syndicationFeed
0x30d2  ldarg.0
0x30d3  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::GenerateSyndicationFeedItems()
0x30d8  callvirt instance void [System.ServiceModel]System.ServiceModel.Syndication.SyndicationFeed::set_Items(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem>)
0x30dd  ldarg.0
0x30de  ldarg.3
0x30df  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteDataRegionFeed(string feedName)
0x30e4  ret
```
