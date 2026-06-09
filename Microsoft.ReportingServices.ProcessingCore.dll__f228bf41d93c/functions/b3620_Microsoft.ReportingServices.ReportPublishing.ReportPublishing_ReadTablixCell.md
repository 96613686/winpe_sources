# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadTablixCell

- ea: `0xb3620`
- end: `0xb3914`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadTablixCell`
- size: `756`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0xb3580`

## callees

- `0x9d040`
- `0x9f860`
- `0x9f890`
- `0xac0b0`
- `0xb3620`
- `0xb3ab0`
- `0xb9c00`
- `0xbcdc0`
- `0xbcde0`
- `0xbce20`
- `0xf48d0`
- `0x111b40`
- `0x13c1f0`
- `0x13c210`
- `0x13c230`
- `0x13c250`
- `0x13c640`
- `0x13c670`
- `0x13c690`
- `0x13c710`
- `0x1767c0`

## string_xrefs

- `0xb36f1`: `StructureTypeOverwrite`

## pseudocode

```c

```

## disassembly

```asm
0xb3620  ldarg.0
0xb3621  call     instance int32 Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GenerateID()
0xb3626  ldarg.1
0xb3627  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.TablixCell::.ctor(int32 id, class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegion dataRegion)
0xb362c  stloc.0
0xb362d  ldarg.0
0xb362e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.IAggregateHolder> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_aggregateHolderList
0xb3633  ldloc.0
0xb3634  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.IAggregateHolder>::Add(var<u1>)
0xb3639  ldarg.0
0xb363a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.IRunningValueHolder> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_runningValueHolderList
0xb363f  ldloc.0
0xb3640  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.IRunningValueHolder>::Add(var<u1>)
0xb3645  ldc.i4.0
0xb3646  stloc.1
0xb3647  ldloca.s 2
0xb3649  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xb364f  ldloca.s 3
0xb3651  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xb3657  ldc.i4.0
0xb3658  stloc.s  4
0xb365a  ldarg.0
0xb365b  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb3660  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xb3665  brtrue   loc_B37CD
0xb366a  ldnull
0xb366b  stloc.s  5
0xb366d  ldnull
0xb366e  stloc.s  6
0xb3670  ldarg.0
0xb3671  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb3676  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xb367b  pop
0xb367c  ldarg.0
0xb367d  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb3682  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xb3687  stloc.s  7
0xb3689  ldloc.s  7
0xb368b  ldc.i4.1
0xb368c  beq.s    loc_B369C
0xb368e  ldloc.s  7
0xb3690  ldc.i4.s 0xF
0xb3692  beq      loc_B379F
0xb3697  br       loc_B37B8
0xb369c  ldarg.0
0xb369d  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb36a2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb36a7  stloc.s  0xA
0xb36a9  ldloc.s  0xA
0xb36ab  ldstr    aDatasetname// "DataSetName"
0xb36b0  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb36b5  brtrue.s loc_B3702
0xb36b7  ldloc.s  0xA
0xb36b9  ldstr    aRelationships// "Relationships"
0xb36be  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb36c3  brtrue.s loc_B3714
0xb36c5  ldloc.s  0xA
0xb36c7  ldstr    aCellcontents// "CellContents"
0xb36cc  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb36d1  brtrue.s loc_B3722
0xb36d3  ldloc.s  0xA
0xb36d5  ldstr    aDataelementnam// "DataElementName"
0xb36da  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb36df  brtrue.s loc_B3746
0xb36e1  ldloc.s  0xA
0xb36e3  ldstr    aDataelementout// "DataElementOutput"
0xb36e8  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb36ed  brtrue.s loc_B3759
0xb36ef  ldloc.s  0xA
0xb36f1  ldstr    aStructuretypeo// "StructureTypeOverwrite"
0xb36f6  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb36fb  brtrue.s loc_B3767
0xb36fd  br       loc_B37B8
0xb3702  ldarg.0
0xb3703  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb3708  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0xb370d  stloc.s  5
0xb370f  br       loc_B37B8
0xb3714  ldarg.0
0xb3715  ldarg.2
0xb3716  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.IdcRelationship> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadRelationships(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xb371b  stloc.s  6
0xb371d  br       loc_B37B8
0xb3722  ldc.i4.1
0xb3723  stloc.s  4
0xb3725  ldloc.0
0xb3726  ldarg.0
0xb3727  ldarg.1
0xb3728  ldarg.2
0xb3729  ldarg.s  4
0xb372b  ldc.i4.1
0xb372c  ldloca.s 8
0xb372e  ldloca.s 2
0xb3730  ldloca.s 3
0xb3732  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadCellContents(class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem parent, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.TextBox> textBoxesWithDefaultSortTarget, bool readRowColSpans, [out] class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem& altCellContents, [out] valuetype [mscorlib]System.Nullable`1<int32>& colSpan, [out] valuetype [mscorlib]System.Nullable`1<int32>& rowSpan)
0xb3737  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.TablixCellBase::set_CellContents(class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem value)
0xb373c  ldloc.0
0xb373d  ldloc.s  8
0xb373f  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.TablixCellBase::set_AltCellContents(class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem value)
0xb3744  br.s     loc_B37B8
0xb3746  ldloc.0
0xb3747  ldarg.0
0xb3748  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb374d  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0xb3752  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.TablixCell::set_DataElementName(string value)
0xb3757  br.s     loc_B37B8
0xb3759  ldloc.0
0xb375a  ldarg.0
0xb375b  call     instance valuetype Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadDataElementOutput()
0xb3760  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.TablixCell::set_DataElementOutput(valuetype Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes value)
0xb3765  br.s     loc_B37B8
0xb3767  ldarg.0
0xb3768  call     instance valuetype Microsoft.ReportingServices.OnDemandReportRendering.StructureTypeOverwriteType Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadStructureTypeOverwrite()
0xb376d  stloc.s  9
0xb376f  ldloca.s 9
0xb3771  constrained. Microsoft.ReportingServices.OnDemandReportRendering.StructureTypeOverwriteType
0xb3777  callvirt instance string [mscorlib]System.Object::ToString()
0xb377c  ldarga.s 2
0xb377e  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xb3783  ldarg.2
0xb3784  ldarg.0
0xb3785  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb378a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb378f  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::ValidateTablixCellStructureTypeOverwrite(string value, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0xb3794  pop
0xb3795  ldloc.0
0xb3796  ldloc.s  9
0xb3798  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.TablixCell::set_StructureTypeOverwrite(valuetype Microsoft.ReportingServices.OnDemandReportRendering.StructureTypeOverwriteType value)
0xb379d  br.s     loc_B37B8
0xb379f  ldstr    aTablixcell// "TablixCell"
0xb37a4  ldarg.0
0xb37a5  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb37aa  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb37af  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb37b4  brfalse.s loc_B37B8
0xb37b6  ldc.i4.1
0xb37b7  stloc.1
0xb37b8  ldloc.1
0xb37b9  brfalse  loc_B3670
0xb37be  ldloc.0
0xb37bf  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataScopeInfo Microsoft.ReportingServices.ReportIntermediateFormat.Cell::get_DataScopeInfo()
0xb37c4  ldloc.s  5
0xb37c6  ldloc.s  6
0xb37c8  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataScopeInfo::SetRelationship(string dataSetName, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.IdcRelationship> relationships)
0xb37cd  ldarg.3
0xb37ce  brfalse.s loc_B3847
0xb37d0  ldloc.s  4
0xb37d2  brfalse.s loc_B37FF
0xb37d4  ldarga.s 2
0xb37d6  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xb37db  ldc.i4   0x13C
0xb37e0  ldc.i4.0
0xb37e1  ldarga.s 2
0xb37e3  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xb37e8  ldarga.s 2
0xb37ea  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xb37ef  ldstr    aTablixcell// "TablixCell"
0xb37f4  call     T0x2B000001
0xb37f9  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0xb37fe  pop
0xb37ff  ldloca.s 2
0xb3801  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xb3806  brfalse  loc_B38CB
0xb380b  ldloca.s 2
0xb380d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xb3812  brfalse  loc_B38CB
0xb3817  ldarga.s 2
0xb3819  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xb381e  ldc.i4   0x13E
0xb3823  ldc.i4.0
0xb3824  ldarga.s 2
0xb3826  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xb382b  ldarga.s 2
0xb382d  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xb3832  ldstr    aColspan// "ColSpan"
0xb3837  call     T0x2B000001
0xb383c  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0xb3841  pop
0xb3842  br       loc_B38CB
0xb3847  ldloc.s  4
0xb3849  brtrue.s loc_B3876
0xb384b  ldarga.s 2
0xb384d  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xb3852  ldc.i4   0x13D
0xb3857  ldc.i4.0
0xb3858  ldarga.s 2
0xb385a  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xb385f  ldarga.s 2
0xb3861  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xb3866  ldstr    aTablixcell// "TablixCell"
0xb386b  call     T0x2B000001
0xb3870  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0xb3875  pop
0xb3876  ldloca.s 2
0xb3878  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xb387d  brtrue.s loc_B3888
0xb387f  ldloc.0
0xb3880  ldc.i4.1
0xb3881  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.TablixCellBase::set_ColSpan(int32 value)
0xb3886  br.s     loc_B38CB
0xb3888  ldloca.s 2
0xb388a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xb388f  brtrue.s loc_B38BE
0xb3891  ldarga.s 2
0xb3893  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xb3898  ldc.i4   0x13E
0xb389d  ldc.i4.0
0xb389e  ldarga.s 2
0xb38a0  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xb38a5  ldarga.s 2
0xb38a7  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xb38ac  ldstr    aColspan// "ColSpan"
0xb38b1  call     T0x2B000001
0xb38b6  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0xb38bb  pop
0xb38bc  br.s     loc_B38CB
0xb38be  ldloc.0
0xb38bf  ldloca.s 2
0xb38c1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xb38c6  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.TablixCellBase::set_ColSpan(int32 value)
0xb38cb  ldloca.s 3
0xb38cd  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xb38d2  brfalse.s loc_B390B
0xb38d4  ldloca.s 3
0xb38d6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xb38db  ldc.i4.1
0xb38dc  beq.s    loc_B390B
0xb38de  ldarga.s 2
0xb38e0  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xb38e5  ldc.i4   0x139
0xb38ea  ldc.i4.0
0xb38eb  ldarga.s 2
0xb38ed  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xb38f2  ldarga.s 2
0xb38f4  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xb38f9  ldstr    aRowspan// "RowSpan"
0xb38fe  call     T0x2B000001
0xb3903  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0xb3908  pop
0xb3909  br.s     loc_B3912
0xb390b  ldloc.0
0xb390c  ldc.i4.1
0xb390d  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.TablixCellBase::set_RowSpan(int32 value)
0xb3912  ldloc.0
0xb3913  ret
```
