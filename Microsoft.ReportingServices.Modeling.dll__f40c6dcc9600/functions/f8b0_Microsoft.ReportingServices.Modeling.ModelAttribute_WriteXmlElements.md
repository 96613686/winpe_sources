# Microsoft.ReportingServices.Modeling.ModelAttribute::WriteXmlElements

- ea: `0xf8b0`
- end: `0xfa23`
- name: `Microsoft.ReportingServices.Modeling.ModelAttribute::WriteXmlElements`
- size: `371`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xb3b0`
- `0xb4b0`
- `0xb530`
- `0xbd60`
- `0xf1b0`
- `0xf8b0`
- `0x132c0`
- `0x14290`
- `0x18f40`

## string_xrefs

- `0xf915`: `OmitSecurityFilters`

## pseudocode

```c

```

## disassembly

```asm
0xf8b0  ldarg.0
0xf8b1  ldarg.1
0xf8b2  call     instance void Microsoft.ReportingServices.Modeling.ModelItem::WriteXmlElements(class Microsoft.ReportingServices.Modeling.ModelingXmlWriter xw)
0xf8b7  ldarg.1
0xf8b8  ldstr    aDatatype// "DataType"
0xf8bd  ldarg.0
0xf8be  ldfld    valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ModelAttribute::m_dataType
0xf8c3  box      Microsoft.ReportingServices.Modeling.DataType
0xf8c8  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteElement(string name, object value)
0xf8cd  ldarg.1
0xf8ce  ldstr    aNullable// "Nullable"
0xf8d3  ldarg.0
0xf8d4  ldfld    bool Microsoft.ReportingServices.Modeling.ModelAttribute::m_nullable
0xf8d9  callvirt T0x2B000048
0xf8de  ldarg.0
0xf8df  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.ModelAttribute::m_expression
0xf8e4  brfalse.s loc_F8F2
0xf8e6  ldarg.0
0xf8e7  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.ModelAttribute::m_expression
0xf8ec  ldarg.1
0xf8ed  callvirt instance void Microsoft.ReportingServices.Modeling.Expression::WriteTo(class Microsoft.ReportingServices.Modeling.ModelingXmlWriter xw)
0xf8f2  ldarg.1
0xf8f3  ldstr    aIsaggregate// "IsAggregate"
0xf8f8  ldarg.0
0xf8f9  ldfld    bool Microsoft.ReportingServices.Modeling.ModelAttribute::m_aggregate
0xf8fe  callvirt T0x2B000048
0xf903  ldarg.1
0xf904  ldstr    aIsfilter// "IsFilter"
0xf909  ldarg.0
0xf90a  ldfld    bool Microsoft.ReportingServices.Modeling.ModelAttribute::m_filter
0xf90f  callvirt T0x2B000048
0xf914  ldarg.1
0xf915  ldstr    aOmitsecurityfi// "OmitSecurityFilters"
0xf91a  ldarg.0
0xf91b  ldfld    bool Microsoft.ReportingServices.Modeling.ModelAttribute::m_omitSecurityFilters
0xf920  callvirt T0x2B000048
0xf925  ldarg.1
0xf926  ldstr    aSortdirection// "SortDirection"
0xf92b  ldarg.0
0xf92c  ldfld    valuetype Microsoft.ReportingServices.Modeling.SortDirection Microsoft.ReportingServices.Modeling.ModelAttribute::m_sortDirection
0xf931  callvirt T0x2B000049
0xf936  ldarg.1
0xf937  ldstr    aWidth// "Width"
0xf93c  ldarg.0
0xf93d  ldfld    int32 Microsoft.ReportingServices.Modeling.ModelAttribute::m_width
0xf942  callvirt T0x2B00004A
0xf947  ldarg.1
0xf948  ldstr    aAlignment// "Alignment"
0xf94d  ldarg.0
0xf94e  ldfld    valuetype Microsoft.ReportingServices.Modeling.Alignment Microsoft.ReportingServices.Modeling.ModelAttribute::m_alignment
0xf953  callvirt T0x2B00004B
0xf958  ldarg.1
0xf959  ldstr    aFormat// "Format"
0xf95e  ldarg.0
0xf95f  ldfld    string Microsoft.ReportingServices.Modeling.ModelAttribute::m_format
0xf964  callvirt T0x2B00004C
0xf969  ldarg.1
0xf96a  ldstr    aMimetype// "MimeType"
0xf96f  ldarg.0
0xf970  ldfld    string Microsoft.ReportingServices.Modeling.ModelAttribute::m_mimeType
0xf975  callvirt T0x2B00004C
0xf97a  ldarg.0
0xf97b  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Modeling.ModelAttribute::m_dataCulture
0xf980  brfalse.s loc_F9AA
0xf982  ldsfld   string [mscorlib]System.String::Empty
0xf987  ldarg.0
0xf988  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Modeling.ModelAttribute::m_dataCulture
0xf98d  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0xf992  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xf997  brfalse.s loc_F9AA
0xf999  ldarg.1
0xf99a  ldstr    aDataculture// "DataCulture"
0xf99f  ldarg.0
0xf9a0  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Modeling.ModelAttribute::m_dataCulture
0xf9a5  callvirt T0x2B00004D
0xf9aa  ldarg.1
0xf9ab  ldstr    aDiscouragegrou// "DiscourageGrouping"
0xf9b0  ldarg.0
0xf9b1  ldfld    bool Microsoft.ReportingServices.Modeling.ModelAttribute::m_discourageGrouping
0xf9b6  callvirt T0x2B000048
0xf9bb  ldarg.1
0xf9bc  ldstr    aEnabledrillthr// "EnableDrillthrough"
0xf9c1  ldarg.0
0xf9c2  ldfld    bool Microsoft.ReportingServices.Modeling.ModelAttribute::m_enableDrillthrough
0xf9c7  callvirt T0x2B000048
0xf9cc  ldarg.1
0xf9cd  ldstr    aContextualname// "ContextualName"
0xf9d2  ldarg.0
0xf9d3  ldfld    valuetype Microsoft.ReportingServices.Modeling.AttributeContextualName Microsoft.ReportingServices.Modeling.ModelAttribute::m_contextualName
0xf9d8  callvirt T0x2B00004E
0xf9dd  ldarg.1
0xf9de  ldstr    aDefaultaggrega// "DefaultAggregateAttributeID"
0xf9e3  ldarg.0
0xf9e4  call     instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.ModelAttribute::get_DefaultAggregate()
0xf9e9  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteReferenceElement(string name, object item)
0xf9ee  ldarg.1
0xf9ef  ldstr    aValueselection// "ValueSelection"
0xf9f4  ldarg.0
0xf9f5  ldfld    valuetype Microsoft.ReportingServices.Modeling.AttributeValueSelection Microsoft.ReportingServices.Modeling.ModelAttribute::m_valueSelection
0xf9fa  callvirt T0x2B00004F
0xf9ff  ldarg.0
0xfa00  ldarg.1
0xfa01  call     instance void Microsoft.ReportingServices.Modeling.ModelField::WriteVariations(class Microsoft.ReportingServices.Modeling.ModelingXmlWriter xw)
0xfa06  ldarg.0
0xfa07  ldfld    class Microsoft.ReportingServices.Modeling.ColumnBinding Microsoft.ReportingServices.Modeling.ModelAttribute::m_binding
0xfa0c  brfalse.s loc_FA22
0xfa0e  ldarg.1
0xfa0f  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlWriter::get_ShouldWriteBindings()
0xfa14  brfalse.s loc_FA22
0xfa16  ldarg.0
0xfa17  ldfld    class Microsoft.ReportingServices.Modeling.ColumnBinding Microsoft.ReportingServices.Modeling.ModelAttribute::m_binding
0xfa1c  ldarg.1
0xfa1d  callvirt instance void Microsoft.ReportingServices.Modeling.Binding::WriteTo(class Microsoft.ReportingServices.Modeling.ModelingXmlWriter xw)
0xfa22  ret
```
