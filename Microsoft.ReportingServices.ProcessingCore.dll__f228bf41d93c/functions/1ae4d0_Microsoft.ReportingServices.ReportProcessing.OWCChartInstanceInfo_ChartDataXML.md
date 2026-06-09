# Microsoft.ReportingServices.ReportProcessing.OWCChartInstanceInfo::ChartDataXML

- ea: `0x1ae4d0`
- end: `0x1ae98f`
- name: `Microsoft.ReportingServices.ReportProcessing.OWCChartInstanceInfo::ChartDataXML`
- size: `1215`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x19680`

## callees

- `0x60e0`
- `0x18f410`
- `0x1a3930`
- `0x1a3c20`
- `0x1ae4d0`

## string_xrefs

- `0x1ae518`: `xmlns`
- `0x1ae52f`: `xmlns`
- `0x1ae546`: `xmlns`
- `0x1ae55d`: `xmlns`
- `0x1ae551`: `urn:schemas-microsoft-com:rowset`
- `0x1ae645`: `writeunknown`

## pseudocode

```c

```

## disassembly

```asm
0x1ae4d0  ldarg.0
0x1ae4d1  ldfld    class Microsoft.ReportingServices.ReportProcessing.ReportItem Microsoft.ReportingServices.ReportProcessing.ReportItemInstanceInfo::m_reportItemDef
0x1ae4d6  castclass Microsoft.ReportingServices.ReportProcessing.OWCChart
0x1ae4db  stloc.0
0x1ae4dc  ldarg.0
0x1ae4dd  ldfld    class Microsoft.ReportingServices.ReportProcessing.VariantList[] Microsoft.ReportingServices.ReportProcessing.OWCChartInstanceInfo::m_chartData
0x1ae4e2  ldc.i4.0
0x1ae4e3  ldelem.ref
0x1ae4e4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x1ae4e9  stloc.1
0x1ae4ea  ldc.i4.0
0x1ae4eb  stloc.2
0x1ae4ec  ldc.i4.0
0x1ae4ed  stloc.3
0x1ae4ee  ldsfld   string [mscorlib]System.String::Empty
0x1ae4f3  stloc.s  4
0x1ae4f5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ae4fa  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x1ae4ff  stloc.s  5
0x1ae501  ldloc.s  5
0x1ae503  newobj   instance void [System.Xml]System.Xml.XmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x1ae508  stloc.s  6
0x1ae50a  ldloc.s  6
0x1ae50c  ldstr    aXml_0// "xml"
0x1ae511  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1ae516  ldloc.s  6
0x1ae518  ldstr    aXmlns// "xmlns"
0x1ae51d  ldstr    aS// "s"
0x1ae522  ldnull
0x1ae523  ldstr    aUuidBdc6e3f06d// "uuid:BDC6E3F0-6DA3-11d1-A2A3-00AA00C148"...
0x1ae528  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x1ae52d  ldloc.s  6
0x1ae52f  ldstr    aXmlns// "xmlns"
0x1ae534  ldstr    aDt_0// "dt"
0x1ae539  ldnull
0x1ae53a  ldstr    aUuidC2f4101065// "uuid:C2F41010-65B3-11d1-A29F-00AA00C148"...
0x1ae53f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x1ae544  ldloc.s  6
0x1ae546  ldstr    aXmlns// "xmlns"
0x1ae54b  ldstr    aRs// "rs"
0x1ae550  ldnull
0x1ae551  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:rowset"
0x1ae556  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x1ae55b  ldloc.s  6
0x1ae55d  ldstr    aXmlns// "xmlns"
0x1ae562  ldstr    aZ// "z"
0x1ae567  ldnull
0x1ae568  ldstr    aRowsetschema// "#RowsetSchema"
0x1ae56d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x1ae572  ldloc.s  6
0x1ae574  ldstr    aS// "s"
0x1ae579  ldstr    aSchema// "Schema"
0x1ae57e  ldnull
0x1ae57f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x1ae584  ldloc.s  6
0x1ae586  ldstr    aId_1// "id"
0x1ae58b  ldstr    aRowsetschema_0// "RowsetSchema"
0x1ae590  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1ae595  ldloc.s  6
0x1ae597  ldstr    aS// "s"
0x1ae59c  ldstr    aElementtype// "ElementType"
0x1ae5a1  ldnull
0x1ae5a2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x1ae5a7  ldloc.s  6
0x1ae5a9  ldstr    aName// "name"
0x1ae5ae  ldstr    aRow_1// "row"
0x1ae5b3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1ae5b8  ldloc.s  6
0x1ae5ba  ldstr    aContent// "content"
0x1ae5bf  ldstr    aEltonly// "eltOnly"
0x1ae5c4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1ae5c9  ldc.i4.0
0x1ae5ca  stloc.2
0x1ae5cb  br       loc_1AE831
0x1ae5d0  ldloc.s  6
0x1ae5d2  ldstr    aS// "s"
0x1ae5d7  ldstr    aAttributetype// "AttributeType"
0x1ae5dc  ldnull
0x1ae5dd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x1ae5e2  ldloc.s  6
0x1ae5e4  ldstr    aName// "name"
0x1ae5e9  ldstr    aC// "c"
0x1ae5ee  ldloca.s 2
0x1ae5f0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ae5f5  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1ae5fa  call     string [mscorlib]System.String::Concat(string, string)
0x1ae5ff  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1ae604  ldloc.s  6
0x1ae606  ldstr    aRs// "rs"
0x1ae60b  ldstr    aName// "name"
0x1ae610  ldnull
0x1ae611  ldloc.0
0x1ae612  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartColumnList Microsoft.ReportingServices.ReportProcessing.OWCChart::get_ChartData()
0x1ae617  ldloc.2
0x1ae618  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartColumn Microsoft.ReportingServices.ReportProcessing.ChartColumnList::get_Item(int32 index)
0x1ae61d  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ChartColumn::get_Name()
0x1ae622  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x1ae627  ldloc.s  6
0x1ae629  ldstr    aRs// "rs"
0x1ae62e  ldstr    aNullable_0// "nullable"
0x1ae633  ldnull
0x1ae634  ldstr    aTrue// "true"
0x1ae639  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x1ae63e  ldloc.s  6
0x1ae640  ldstr    aRs// "rs"
0x1ae645  ldstr    aWriteunknown// "writeunknown"
0x1ae64a  ldnull
0x1ae64b  ldstr    aTrue// "true"
0x1ae650  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x1ae655  ldloc.s  6
0x1ae657  ldstr    aS// "s"
0x1ae65c  ldstr    aDatatype_0// "datatype"
0x1ae661  ldnull
0x1ae662  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x1ae667  ldc.i4.0
0x1ae668  stloc.3
0x1ae669  br.s     loc_1AE66F
0x1ae66b  ldloc.3
0x1ae66c  ldc.i4.1
0x1ae66d  add
0x1ae66e  stloc.3
0x1ae66f  ldloc.3
0x1ae670  ldarg.0
0x1ae671  ldfld    class Microsoft.ReportingServices.ReportProcessing.VariantList[] Microsoft.ReportingServices.ReportProcessing.OWCChartInstanceInfo::m_chartData
0x1ae676  ldloc.2
0x1ae677  ldelem.ref
0x1ae678  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x1ae67d  bge.s    loc_1AE68F
0x1ae67f  ldarg.0
0x1ae680  ldfld    class Microsoft.ReportingServices.ReportProcessing.VariantList[] Microsoft.ReportingServices.ReportProcessing.OWCChartInstanceInfo::m_chartData
0x1ae685  ldloc.2
0x1ae686  ldelem.ref
0x1ae687  ldloc.3
0x1ae688  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x1ae68d  brfalse.s loc_1AE66B
0x1ae68f  ldloc.3
0x1ae690  ldarg.0
0x1ae691  ldfld    class Microsoft.ReportingServices.ReportProcessing.VariantList[] Microsoft.ReportingServices.ReportProcessing.OWCChartInstanceInfo::m_chartData
0x1ae696  ldloc.2
0x1ae697  ldelem.ref
0x1ae698  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x1ae69d  bge      loc_1AE7ED
0x1ae6a2  ldarg.0
0x1ae6a3  ldfld    class Microsoft.ReportingServices.ReportProcessing.VariantList[] Microsoft.ReportingServices.ReportProcessing.OWCChartInstanceInfo::m_chartData
0x1ae6a8  ldloc.2
0x1ae6a9  ldelem.ref
0x1ae6aa  ldloc.3
0x1ae6ab  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x1ae6b0  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1ae6b5  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x1ae6ba  stloc.s  9
0x1ae6bc  ldloc.s  9
0x1ae6be  ldc.i4.1
0x1ae6bf  sub
0x1ae6c0  switch   loc_1AE784, loc_1AE7E4, loc_1AE712, loc_1AE72A, loc_1AE7C0, loc_1AE71E, loc_1AE766, loc_1AE7C9, loc_1AE772, loc_1AE7D2, loc_1AE77B, loc_1AE7DB, loc_1AE742, loc_1AE74E, loc_1AE75A, loc_1AE736, loc_1AE7E4, loc_1AE7E4
0x1ae70d  br       loc_1AE7E4
0x1ae712  ldstr    aBoolean_0// "boolean"
0x1ae717  stloc.s  4
0x1ae719  br       loc_1AE7F4
0x1ae71e  ldstr    aUi1// "ui1"
0x1ae723  stloc.s  4
0x1ae725  br       loc_1AE7F4
0x1ae72a  ldstr    aChar// "char"
0x1ae72f  stloc.s  4
0x1ae731  br       loc_1AE7F4
0x1ae736  ldstr    aDatetime_0// "dateTime"
0x1ae73b  stloc.s  4
0x1ae73d  br       loc_1AE7F4
0x1ae742  ldstr    aR4// "r4"
0x1ae747  stloc.s  4
0x1ae749  br       loc_1AE7F4
0x1ae74e  ldstr    aFloat_0// "float"
0x1ae753  stloc.s  4
0x1ae755  br       loc_1AE7F4
0x1ae75a  ldstr    aR8// "r8"
0x1ae75f  stloc.s  4
0x1ae761  br       loc_1AE7F4
0x1ae766  ldstr    aI2// "i2"
0x1ae76b  stloc.s  4
0x1ae76d  br       loc_1AE7F4
0x1ae772  ldstr    aI4// "i4"
0x1ae777  stloc.s  4
0x1ae779  br.s     loc_1AE7F4
0x1ae77b  ldstr    aI8// "i8"
0x1ae780  stloc.s  4
0x1ae782  br.s     loc_1AE7F4
0x1ae784  ldarg.0
0x1ae785  ldfld    class Microsoft.ReportingServices.ReportProcessing.VariantList[] Microsoft.ReportingServices.ReportProcessing.OWCChartInstanceInfo::m_chartData
0x1ae78a  ldloc.2
0x1ae78b  ldelem.ref
0x1ae78c  ldloc.3
0x1ae78d  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x1ae792  isinst   [mscorlib]System.TimeSpan
0x1ae797  brfalse.s loc_1AE7A2
0x1ae799  ldstr    aTime// "time"
0x1ae79e  stloc.s  4
0x1ae7a0  br.s     loc_1AE7F4
0x1ae7a2  ldarg.0
0x1ae7a3  ldfld    class Microsoft.ReportingServices.ReportProcessing.VariantList[] Microsoft.ReportingServices.ReportProcessing.OWCChartInstanceInfo::m_chartData
0x1ae7a8  ldloc.2
0x1ae7a9  ldelem.ref
0x1ae7aa  ldloc.3
0x1ae7ab  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x1ae7b0  isinst   unsigned int8[]
0x1ae7b5  brfalse.s loc_1AE7F4
0x1ae7b7  ldstr    aBinHex// "bin.hex"
0x1ae7bc  stloc.s  4
0x1ae7be  br.s     loc_1AE7F4
0x1ae7c0  ldstr    aI1// "i1"
0x1ae7c5  stloc.s  4
0x1ae7c7  br.s     loc_1AE7F4
0x1ae7c9  ldstr    aUi2// "ui2"
0x1ae7ce  stloc.s  4
0x1ae7d0  br.s     loc_1AE7F4
0x1ae7d2  ldstr    aUi4// "ui4"
0x1ae7d7  stloc.s  4
0x1ae7d9  br.s     loc_1AE7F4
0x1ae7db  ldstr    aUi8// "ui8"
0x1ae7e0  stloc.s  4
0x1ae7e2  br.s     loc_1AE7F4
0x1ae7e4  ldstr    aString_1// "string"
0x1ae7e9  stloc.s  4
0x1ae7eb  br.s     loc_1AE7F4
0x1ae7ed  ldstr    aString_1// "string"
0x1ae7f2  stloc.s  4
0x1ae7f4  ldloc.s  6
0x1ae7f6  ldstr    aDt_0// "dt"
0x1ae7fb  ldstr    aType_2// "type"
0x1ae800  ldnull
0x1ae801  ldloc.s  4
0x1ae803  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x1ae808  ldloc.s  6
0x1ae80a  ldstr    aRs// "rs"
0x1ae80f  ldstr    aFixedlength// "fixedlength"
0x1ae814  ldnull
0x1ae815  ldstr    aTrue// "true"
0x1ae81a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x1ae81f  ldloc.s  6
0x1ae821  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1ae826  ldloc.s  6
0x1ae828  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1ae82d  ldloc.2
0x1ae82e  ldc.i4.1
0x1ae82f  add
0x1ae830  stloc.2
0x1ae831  ldloc.2
0x1ae832  ldloc.0
0x1ae833  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartColumnList Microsoft.ReportingServices.ReportProcessing.OWCChart::get_ChartData()
0x1ae838  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x1ae83d  blt      loc_1AE5D0
0x1ae842  ldloc.s  6
0x1ae844  ldstr    aS// "s"
0x1ae849  ldstr    aExtends// "extends"
0x1ae84e  ldnull
0x1ae84f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x1ae854  ldloc.s  6
0x1ae856  ldstr    aType_2// "type"
0x1ae85b  ldstr    aRsRowbase// "rs:rowbase"
0x1ae860  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x1ae865  ldloc.s  6
0x1ae867  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1ae86c  ldloc.s  6
0x1ae86e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1ae873  ldloc.s  6
0x1ae875  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1ae87a  ldloc.s  6
0x1ae87c  ldstr    aRs// "rs"
0x1ae881  ldstr    aData// "data"
0x1ae886  ldnull
0x1ae887  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x1ae88c  ldc.i4.1
0x1ae88d  stloc.s  7
0x1ae88f  ldnull
0x1ae890  stloc.s  8
0x1ae892  ldc.i4.0
0x1ae893  stloc.s  0xA
0x1ae895  br       loc_1AE96B
0x1ae89a  ldc.i4.0
0x1ae89b  stloc.2
0x1ae89c  br.s     loc_1AE8B8
0x1ae89e  ldarg.0
0x1ae89f  ldfld    class Microsoft.ReportingServices.ReportProcessing.VariantList[] Microsoft.ReportingServices.ReportProcessing.OWCChartInstanceInfo::m_chartData
0x1ae8a4  ldloc.2
0x1ae8a5  ldelem.ref
0x1ae8a6  ldloc.s  0xA
0x1ae8a8  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x1ae8ad  brfalse.s loc_1AE8B4
0x1ae8af  ldc.i4.0
0x1ae8b0  stloc.s  7
0x1ae8b2  br.s     loc_1AE8C6
0x1ae8b4  ldloc.2
0x1ae8b5  ldc.i4.1
0x1ae8b6  add
0x1ae8b7  stloc.2
0x1ae8b8  ldloc.2
0x1ae8b9  ldloc.0
0x1ae8ba  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartColumnList Microsoft.ReportingServices.ReportProcessing.OWCChart::get_ChartData()
0x1ae8bf  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x1ae8c4  blt.s    loc_1AE89E
0x1ae8c6  ldloc.s  7
  ... truncated ...
```
