# Microsoft.ReportingServices.Modeling.ModelAttribute::LoadXmlElement

- ea: `0xf4b0`
- end: `0xf861`
- name: `Microsoft.ReportingServices.Modeling.ModelAttribute::LoadXmlElement`
- size: `945`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa740`
- `0xa760`
- `0xa7b0`
- `0xa9e0`
- `0xaa10`
- `0xaa40`
- `0xaa90`
- `0xaec0`
- `0xb1c0`
- `0xc470`
- `0xf260`
- `0xf4b0`
- `0x13250`
- `0x186a0`
- `0x18d00`

## string_xrefs

- `0xf65f`: `OmitSecurityFilters`

## pseudocode

```c

```

## disassembly

```asm
0xf4b0  ldarg.1
0xf4b1  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_IsDefaultNamespace()
0xf4b6  brfalse  loc_F859
0xf4bb  ldarg.1
0xf4bc  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName()
0xf4c1  stloc.0
0xf4c2  ldloc.0
0xf4c3  brfalse  loc_F859
0xf4c8  ldloc.0
0xf4c9  call     instance int32 [mscorlib]System.String::get_Length()
0xf4ce  stloc.1
0xf4cf  ldloc.1
0xf4d0  ldc.i4.5
0xf4d1  sub
0xf4d2  switch   loc_F688, loc_F574, loc_F859, loc_F520, loc_F69D, loc_F61F, loc_F557, loc_F859, loc_F673, loc_F5AE, loc_F859, loc_F859, loc_F859, loc_F591, loc_F65E
0xf513  ldloc.1
0xf514  ldc.i4.s 0x1B
0xf516  beq      loc_F730
0xf51b  br       loc_F859
0xf520  ldloc.0
0xf521  ldc.i4.0
0xf522  call     instance char [mscorlib]System.String::get_Chars(int32)
0xf527  stloc.2
0xf528  ldloc.2
0xf529  ldc.i4.s 0x49
0xf52b  bgt.un.s loc_F542
0xf52d  ldloc.2
0xf52e  ldc.i4.s 0x44
0xf530  beq      loc_F5CB
0xf535  ldloc.2
0xf536  ldc.i4.s 0x49
0xf538  beq      loc_F5F5
0xf53d  br       loc_F859
0xf542  ldloc.2
0xf543  ldc.i4.s 0x4D
0xf545  beq      loc_F60A
0xf54a  ldloc.2
0xf54b  ldc.i4.s 0x4E
0xf54d  beq      loc_F5E0
0xf552  br       loc_F859
0xf557  ldloc.0
0xf558  ldc.i4.0
0xf559  call     instance char [mscorlib]System.String::get_Chars(int32)
0xf55e  stloc.2
0xf55f  ldloc.2
0xf560  ldc.i4.s 0x44
0xf562  beq      loc_F649
0xf567  ldloc.2
0xf568  ldc.i4.s 0x49
0xf56a  beq      loc_F634
0xf56f  br       loc_F859
0xf574  ldloc.0
0xf575  ldc.i4.0
0xf576  call     instance char [mscorlib]System.String::get_Chars(int32)
0xf57b  stloc.2
0xf57c  ldloc.2
0xf57d  ldc.i4.s 0x43
0xf57f  beq      loc_F6C7
0xf584  ldloc.2
0xf585  ldc.i4.s 0x46
0xf587  beq      loc_F6B2
0xf58c  br       loc_F859
0xf591  ldloc.0
0xf592  ldc.i4.0
0xf593  call     instance char [mscorlib]System.String::get_Chars(int32)
0xf598  stloc.2
0xf599  ldloc.2
0xf59a  ldc.i4.s 0x44
0xf59c  beq      loc_F6DC
0xf5a1  ldloc.2
0xf5a2  ldc.i4.s 0x45
0xf5a4  beq      loc_F6F1
0xf5a9  br       loc_F859
0xf5ae  ldloc.0
0xf5af  ldc.i4.0
0xf5b0  call     instance char [mscorlib]System.String::get_Chars(int32)
0xf5b5  stloc.2
0xf5b6  ldloc.2
0xf5b7  ldc.i4.s 0x43
0xf5b9  beq      loc_F706
0xf5be  ldloc.2
0xf5bf  ldc.i4.s 0x56
0xf5c1  beq      loc_F71B
0xf5c6  br       loc_F859
0xf5cb  ldloc.0
0xf5cc  ldstr    aDatatype// "DataType"
0xf5d1  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf5d6  brtrue   loc_F745
0xf5db  br       loc_F859
0xf5e0  ldloc.0
0xf5e1  ldstr    aNullable// "Nullable"
0xf5e6  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf5eb  brtrue   loc_F753
0xf5f0  br       loc_F859
0xf5f5  ldloc.0
0xf5f6  ldstr    aIsfilter// "IsFilter"
0xf5fb  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf600  brtrue   loc_F789
0xf605  br       loc_F859
0xf60a  ldloc.0
0xf60b  ldstr    aMimetype// "MimeType"
0xf610  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf615  brtrue   loc_F7DD
0xf61a  br       loc_F859
0xf61f  ldloc.0
0xf620  ldstr    aExpression// "Expression"
0xf625  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf62a  brtrue   loc_F761
0xf62f  br       loc_F859
0xf634  ldloc.0
0xf635  ldstr    aIsaggregate// "IsAggregate"
0xf63a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf63f  brtrue   loc_F77B
0xf644  br       loc_F859
0xf649  ldloc.0
0xf64a  ldstr    aDataculture// "DataCulture"
0xf64f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf654  brtrue   loc_F7EB
0xf659  br       loc_F859
0xf65e  ldloc.0
0xf65f  ldstr    aOmitsecurityfi// "OmitSecurityFilters"
0xf664  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf669  brtrue   loc_F797
0xf66e  br       loc_F859
0xf673  ldloc.0
0xf674  ldstr    aSortdirection// "SortDirection"
0xf679  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf67e  brtrue   loc_F7A5
0xf683  br       loc_F859
0xf688  ldloc.0
0xf689  ldstr    aWidth// "Width"
0xf68e  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf693  brtrue   loc_F7B3
0xf698  br       loc_F859
0xf69d  ldloc.0
0xf69e  ldstr    aAlignment// "Alignment"
0xf6a3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf6a8  brtrue   loc_F7C1
0xf6ad  br       loc_F859
0xf6b2  ldloc.0
0xf6b3  ldstr    aFormat// "Format"
0xf6b8  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf6bd  brtrue   loc_F7CF
0xf6c2  br       loc_F859
0xf6c7  ldloc.0
0xf6c8  ldstr    aColumn// "Column"
0xf6cd  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf6d2  brtrue   loc_F84B
0xf6d7  br       loc_F859
0xf6dc  ldloc.0
0xf6dd  ldstr    aDiscouragegrou// "DiscourageGrouping"
0xf6e2  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf6e7  brtrue   loc_F7F9
0xf6ec  br       loc_F859
0xf6f1  ldloc.0
0xf6f2  ldstr    aEnabledrillthr// "EnableDrillthrough"
0xf6f7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf6fc  brtrue   loc_F807
0xf701  br       loc_F859
0xf706  ldloc.0
0xf707  ldstr    aContextualname// "ContextualName"
0xf70c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf711  brtrue   loc_F815
0xf716  br       loc_F859
0xf71b  ldloc.0
0xf71c  ldstr    aValueselection// "ValueSelection"
0xf721  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf726  brtrue   loc_F83D
0xf72b  br       loc_F859
0xf730  ldloc.0
0xf731  ldstr    aDefaultaggrega// "DefaultAggregateAttributeID"
0xf736  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf73b  brtrue   loc_F823
0xf740  br       loc_F859
0xf745  ldarg.0
0xf746  ldarg.1
0xf747  callvirt T0x2B000042
0xf74c  stfld    valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ModelAttribute::m_dataType
0xf751  ldc.i4.1
0xf752  ret
0xf753  ldarg.0
0xf754  ldarg.1
0xf755  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsBoolean()
0xf75a  stfld    bool Microsoft.ReportingServices.Modeling.ModelAttribute::m_nullable
0xf75f  ldc.i4.1
0xf760  ret
0xf761  ldarg.0
0xf762  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor()
0xf767  stfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.ModelAttribute::m_expression
0xf76c  ldarg.0
0xf76d  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.ModelAttribute::m_expression
0xf772  ldarg.1
0xf773  ldc.i4.0
0xf774  callvirt instance void Microsoft.ReportingServices.Modeling.Expression::Load(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr, bool named)
0xf779  ldc.i4.1
0xf77a  ret
0xf77b  ldarg.0
0xf77c  ldarg.1
0xf77d  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsBoolean()
0xf782  stfld    bool Microsoft.ReportingServices.Modeling.ModelAttribute::m_aggregate
0xf787  ldc.i4.1
0xf788  ret
0xf789  ldarg.0
0xf78a  ldarg.1
0xf78b  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsBoolean()
0xf790  stfld    bool Microsoft.ReportingServices.Modeling.ModelAttribute::m_filter
0xf795  ldc.i4.1
0xf796  ret
0xf797  ldarg.0
0xf798  ldarg.1
0xf799  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsBoolean()
0xf79e  stfld    bool Microsoft.ReportingServices.Modeling.ModelAttribute::m_omitSecurityFilters
0xf7a3  ldc.i4.1
0xf7a4  ret
0xf7a5  ldarg.0
0xf7a6  ldarg.1
0xf7a7  callvirt T0x2B000043
0xf7ac  stfld    valuetype Microsoft.ReportingServices.Modeling.SortDirection Microsoft.ReportingServices.Modeling.ModelAttribute::m_sortDirection
0xf7b1  ldc.i4.1
0xf7b2  ret
0xf7b3  ldarg.0
0xf7b4  ldarg.1
0xf7b5  callvirt instance int32 Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsInt()
0xf7ba  stfld    int32 Microsoft.ReportingServices.Modeling.ModelAttribute::m_width
0xf7bf  ldc.i4.1
0xf7c0  ret
0xf7c1  ldarg.0
0xf7c2  ldarg.1
0xf7c3  callvirt T0x2B000044
0xf7c8  stfld    valuetype Microsoft.ReportingServices.Modeling.Alignment Microsoft.ReportingServices.Modeling.ModelAttribute::m_alignment
0xf7cd  ldc.i4.1
0xf7ce  ret
0xf7cf  ldarg.0
0xf7d0  ldarg.1
0xf7d1  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsString()
0xf7d6  stfld    string Microsoft.ReportingServices.Modeling.ModelAttribute::m_format
0xf7db  ldc.i4.1
0xf7dc  ret
0xf7dd  ldarg.0
0xf7de  ldarg.1
0xf7df  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsString()
0xf7e4  stfld    string Microsoft.ReportingServices.Modeling.ModelAttribute::m_mimeType
0xf7e9  ldc.i4.1
0xf7ea  ret
0xf7eb  ldarg.0
0xf7ec  ldarg.1
0xf7ed  callvirt instance class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsCultureInfo()
0xf7f2  stfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Modeling.ModelAttribute::m_dataCulture
0xf7f7  ldc.i4.1
0xf7f8  ret
0xf7f9  ldarg.0
0xf7fa  ldarg.1
0xf7fb  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsBoolean()
0xf800  stfld    bool Microsoft.ReportingServices.Modeling.ModelAttribute::m_discourageGrouping
0xf805  ldc.i4.1
0xf806  ret
0xf807  ldarg.0
0xf808  ldarg.1
0xf809  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsBoolean()
0xf80e  stfld    bool Microsoft.ReportingServices.Modeling.ModelAttribute::m_enableDrillthrough
0xf813  ldc.i4.1
0xf814  ret
0xf815  ldarg.0
0xf816  ldarg.1
0xf817  callvirt T0x2B000045
0xf81c  stfld    valuetype Microsoft.ReportingServices.Modeling.AttributeContextualName Microsoft.ReportingServices.Modeling.ModelAttribute::m_contextualName
0xf821  ldc.i4.1
0xf822  ret
0xf823  ldarg.1
0xf824  callvirt instance class Microsoft.ReportingServices.Modeling.DeserializationContext Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Context()
0xf829  ldarg.0
0xf82a  ldarg.1
0xf82b  ldstr    aDefaultaggrega// "DefaultAggregateAttributeID"
0xf830  ldc.i4.0
0xf831  callvirt instance valuetype Microsoft.ReportingServices.Modeling.ModelingReference Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadReferenceByID(string propertyName, bool multipleInScope)
0xf836  callvirt instance void Microsoft.ReportingServices.Modeling.DeserializationContext::AddReference(class Microsoft.ReportingServices.Modeling.IDeserializationCallback item, valuetype Microsoft.ReportingServices.Modeling.ModelingReference reference)
0xf83b  ldc.i4.1
0xf83c  ret
0xf83d  ldarg.0
0xf83e  ldarg.1
0xf83f  callvirt T0x2B000046
0xf844  stfld    valuetype Microsoft.ReportingServices.Modeling.AttributeValueSelection Microsoft.ReportingServices.Modeling.ModelAttribute::m_valueSelection
0xf849  ldc.i4.1
0xf84a  ret
0xf84b  ldarg.0
0xf84c  ldarg.1
0xf84d  call     class Microsoft.ReportingServices.Modeling.ColumnBinding Microsoft.ReportingServices.Modeling.ColumnBinding::FromReader(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0xf852  call     instance void Microsoft.ReportingServices.Modeling.ModelAttribute::set_Binding(class Microsoft.ReportingServices.Modeling.ColumnBinding value)
0xf857  ldc.i4.1
0xf858  ret
0xf859  ldarg.0
0xf85a  ldarg.1
0xf85b  call     instance bool Microsoft.ReportingServices.Modeling.ModelField::LoadXmlElement(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0xf860  ret
```
