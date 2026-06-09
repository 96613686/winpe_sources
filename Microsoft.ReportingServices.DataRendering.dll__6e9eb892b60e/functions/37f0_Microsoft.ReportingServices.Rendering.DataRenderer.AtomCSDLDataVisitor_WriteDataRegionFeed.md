# Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLDataVisitor::WriteDataRegionFeed

- ea: `0x37f0`
- end: `0x3953`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLDataVisitor::WriteDataRegionFeed`
- size: `355`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x37f0`
- `0x3960`
- `0x3eb0`

## string_xrefs

- `0x384a`: `http://schemas.microsoft.com/sqlserver/reporting/2010/01/feedmetadata`

## pseudocode

```c

```

## disassembly

```asm
0x37f0  ldarg.0
0x37f1  ldfld    class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationFeed Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_syndicationFeed
0x37f6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem> [System.ServiceModel]System.ServiceModel.Syndication.SyndicationFeed::get_Items()
0x37fb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem>::GetEnumerator()
0x3800  dup
0x3801  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3806  pop
0x3807  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x380c  isinst   [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem
0x3811  stloc.0
0x3812  ldarg.0
0x3813  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x3818  ldstr    aEntitytype// "EntityType"
0x381d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x3822  ldarg.0
0x3823  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x3828  ldstr    aName// "Name"
0x382d  ldarg.1
0x382e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x3833  ldarg.0
0x3834  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_reportItem
0x3839  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLDataVisitor::GetDataRegionType(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem reportItem)
0x383e  stloc.1
0x383f  ldarg.0
0x3840  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x3845  ldstr    aDataregiontype// "DataRegionType"
0x384a  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/sqlserver/"...
0x384f  ldloc.1
0x3850  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string)
0x3855  ldarg.0
0x3856  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x385b  ldstr    aKey// "Key"
0x3860  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x3865  ldarg.0
0x3866  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x386b  ldstr    aPropertyref// "PropertyRef"
0x3870  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x3875  ldarg.0
0x3876  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x387b  ldstr    aName// "Name"
0x3880  ldstr    aKey// "Key"
0x3885  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x388a  ldarg.0
0x388b  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x3890  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x3895  ldarg.0
0x3896  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x389b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x38a0  ldarg.0
0x38a1  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x38a6  ldstr    aProperty// "Property"
0x38ab  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x38b0  ldarg.0
0x38b1  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x38b6  ldstr    aName// "Name"
0x38bb  ldstr    aKey// "Key"
0x38c0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x38c5  ldarg.0
0x38c6  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x38cb  ldstr    aType// "Type"
0x38d0  ldstr    aEdmString// "Edm.String"
0x38d5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x38da  ldarg.0
0x38db  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x38e0  ldstr    aNullable// "Nullable"
0x38e5  ldstr    aFalse// "false"
0x38ea  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x38ef  ldarg.0
0x38f0  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x38f5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x38fa  ldloc.0
0x38fb  brfalse.s loc_3947
0x38fd  ldloc.0
0x38fe  callvirt instance class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationContent [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem::get_Content()
0x3903  castclass Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent
0x3908  ldc.i4.0
0x3909  stloc.2
0x390a  ldarg.0
0x390b  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterCollection Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_reportParamters
0x3910  brfalse.s loc_391E
0x3912  ldarg.0
0x3913  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterCollection Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_reportParamters
0x3918  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameter>::get_Count()
0x391d  stloc.2
0x391e  ldc.i4.0
0x391f  stloc.3
0x3920  ldarg.0
0x3921  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TypedColumnValue> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_feedLevelRowContent
0x3926  brfalse.s loc_3934
0x3928  ldarg.0
0x3929  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TypedColumnValue> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_feedLevelRowContent
0x392e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class TypedColumnValue>::get_Count()
0x3933  stloc.3
0x3934  ldarg.0
0x3935  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x393a  ldarg.0
0x393b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ReportingServices.Rendering.DataRenderer.ColumnMetadata> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnMetadata
0x3940  ldloc.2
0x3941  ldloc.3
0x3942  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::WriteRowContentsCSDL(class [System.Xml]System.Xml.XmlWriter xmlWriter, class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ReportingServices.Rendering.DataRenderer.ColumnMetadata> metadata, int32 reportParameterCount, int32 feedLevelColumnCount)
0x3947  ldarg.0
0x3948  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x394d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x3952  ret
```
