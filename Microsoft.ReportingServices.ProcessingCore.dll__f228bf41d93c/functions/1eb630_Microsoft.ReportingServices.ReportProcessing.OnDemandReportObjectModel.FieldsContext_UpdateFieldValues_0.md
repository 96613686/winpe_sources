# Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::UpdateFieldValues_0

- ea: `0x1eb630`
- end: `0x1eb937`
- name: `Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::UpdateFieldValues_0`
- size: `775`
- prototype: ``
- caller_count: `2`
- callee_count: `34`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1eae50`
- `0x1eb5f0`

## callees

- `0xd8700`
- `0xd8750`
- `0xd9080`
- `0xd90b0`
- `0x113d00`
- `0x113f10`
- `0x113fe0`
- `0x114310`
- `0x114bc0`
- `0x1211c0`
- `0x1211e0`
- `0x121200`
- `0x1216f0`
- `0x121710`
- `0x121730`
- `0x121780`
- `0x15b500`
- `0x1c5030`
- `0x1eb180`
- `0x1eb4f0`
- `0x1eb630`
- `0x1eb940`
- `0x1ebb10`
- `0x1ebb70`
- `0x1ebbd0`
- `0x1ebc20`
- `0x1ebc40`
- `0x1ebc50`
- `0x1ec210`
- `0x1ec230`
- `0x1ec270`
- `0x1ec2b0`
- `0x1ec6b0`
- `0x1fb4d0`

## string_xrefs

- `0x1eb63a`: `Empty data row / no data reader`

## pseudocode

```c

```

## disassembly

```asm
0x1eb630  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1eb635  ldarg.s  4
0x1eb637  ldnull
0x1eb638  cgt.un
0x1eb63a  ldstr    aEmptyDataRowNo// "Empty data row / no data reader"
0x1eb63f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1eb644  ldarg.0
0x1eb645  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_dataSetInstance
0x1eb64a  ldarg.s  5
0x1eb64c  beq.s    loc_1EB6AE
0x1eb64e  ldarg.0
0x1eb64f  ldarg.s  5
0x1eb651  stfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_dataSetInstance
0x1eb656  ldarg.0
0x1eb657  ldarg.s  5
0x1eb659  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance::get_DataSetDef()
0x1eb65e  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_DataSetCore()
0x1eb663  stfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_dataSet
0x1eb668  ldarg.0
0x1eb669  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_dataSet
0x1eb66e  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore::get_FieldsContext()
0x1eb673  ldnull
0x1eb674  cgt.un
0x1eb676  ldarg.2
0x1eb677  and
0x1eb678  brfalse.s loc_1EB692
0x1eb67a  ldarg.0
0x1eb67b  ldarg.0
0x1eb67c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_dataSet
0x1eb681  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore::get_FieldsContext()
0x1eb686  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::get_Fields()
0x1eb68b  stfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_fields
0x1eb690  br.s     loc_1EB695
0x1eb692  ldc.i4.0
0x1eb693  starg.s  3
0x1eb695  ldarg.0
0x1eb696  ldnull
0x1eb697  stfld    class DataChunkReader Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_dataReader
0x1eb69c  ldarg.0
0x1eb69d  ldsfld   int64 Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataFieldRow::UnInitializedStreamOffset
0x1eb6a2  stfld    int64 Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_lastRowOffset
0x1eb6a7  ldarg.0
0x1eb6a8  ldc.i4.0
0x1eb6a9  stfld    bool Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_pendingFieldValueUpdate
0x1eb6ae  ldarg.0
0x1eb6af  ldc.i4.0
0x1eb6b0  stfld    bool Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_allFieldsCleared
0x1eb6b5  ldarg.s  5
0x1eb6b7  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.FieldInfo[] Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance::get_FieldInfos()
0x1eb6bc  stloc.0
0x1eb6bd  ldarg.0
0x1eb6be  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_fields
0x1eb6c3  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::get_ReaderExtensionsSupported()
0x1eb6c8  brfalse.s loc_1EB717
0x1eb6ca  ldarg.0
0x1eb6cb  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_dataSet
0x1eb6d0  callvirt instance valuetype TriState Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore::get_InterpretSubtotalsAsDetails()
0x1eb6d5  ldc.i4.2
0x1eb6d6  bne.un.s loc_1EB717
0x1eb6d8  ldarg.0
0x1eb6d9  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_fields
0x1eb6de  ldarg.s  4
0x1eb6e0  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.RecordRow::get_IsAggregateRow()
0x1eb6e5  callvirt instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::set_IsAggregateRow(bool value)
0x1eb6ea  ldarg.0
0x1eb6eb  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_fields
0x1eb6f0  ldarg.s  4
0x1eb6f2  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.RecordRow::get_AggregationFieldCount()
0x1eb6f7  callvirt instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::set_AggregationFieldCount(int32 value)
0x1eb6fc  ldarg.s  4
0x1eb6fe  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.RecordRow::get_IsAggregateRow()
0x1eb703  brtrue.s loc_1EB717
0x1eb705  ldarg.0
0x1eb706  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_fields
0x1eb70b  ldarg.s  4
0x1eb70d  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.RecordRow::get_AggregationFieldCount()
0x1eb712  callvirt instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::set_AggregationFieldCountForDetailRow(int32 value)
0x1eb717  ldc.i4.0
0x1eb718  stloc.1
0x1eb719  ldarg.0
0x1eb71a  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_dataSet
0x1eb71f  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Field> Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore::get_Fields()
0x1eb724  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Field>::get_Count()
0x1eb729  stloc.2
0x1eb72a  ldarg.s  4
0x1eb72c  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.RecordField[] Microsoft.ReportingServices.ReportIntermediateFormat.RecordRow::get_RecordFields()
0x1eb731  ldlen
0x1eb732  conv.i4
0x1eb733  stloc.3
0x1eb734  ldc.i4.0
0x1eb735  stloc.1
0x1eb736  br       loc_1EB88D
0x1eb73b  ldarg.3
0x1eb73c  brtrue.s loc_1EB741
0x1eb73e  ldnull
0x1eb73f  br.s     loc_1EB74D
0x1eb741  ldarg.0
0x1eb742  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_fields
0x1eb747  ldloc.1
0x1eb748  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::GetFieldByIndex(int32 index)
0x1eb74d  stloc.s  4
0x1eb74f  ldarg.0
0x1eb750  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_dataSet
0x1eb755  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Field> Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore::get_Fields()
0x1eb75a  ldloc.1
0x1eb75b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Field>::get_Item(!!T0)
0x1eb760  stloc.s  5
0x1eb762  ldarg.s  4
0x1eb764  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.RecordField[] Microsoft.ReportingServices.ReportIntermediateFormat.RecordRow::get_RecordFields()
0x1eb769  ldloc.1
0x1eb76a  ldelem.ref
0x1eb76b  stloc.s  6
0x1eb76d  ldloc.s  6
0x1eb76f  brtrue.s loc_1EB799
0x1eb771  ldarg.3
0x1eb772  brfalse.s loc_1EB778
0x1eb774  ldloc.s  4
0x1eb776  brtrue.s loc_1EB789
0x1eb778  ldarg.1
0x1eb779  ldc.i4.4
0x1eb77a  ldnull
0x1eb77b  ldloc.s  5
0x1eb77d  newobj   instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldImpl::.ctor(class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl reportOM, valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus status, string exceptionMessage, class Microsoft.ReportingServices.ReportIntermediateFormat.Field fieldDef)
0x1eb782  stloc.s  4
0x1eb784  br       loc_1EB820
0x1eb789  ldloc.s  4
0x1eb78b  ldnull
0x1eb78c  ldc.i4.0
0x1eb78d  ldc.i4.4
0x1eb78e  ldnull
0x1eb78f  callvirt instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldImpl::UpdateValue(object value, bool isAggregationField, valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus status, string exceptionMessage)
0x1eb794  br       loc_1EB820
0x1eb799  ldloc.s  6
0x1eb79b  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus Microsoft.ReportingServices.ReportIntermediateFormat.RecordField::get_FieldStatus()
0x1eb7a0  brtrue.s loc_1EB7DC
0x1eb7a2  ldarg.3
0x1eb7a3  brfalse.s loc_1EB7A9
0x1eb7a5  ldloc.s  4
0x1eb7a7  brtrue.s loc_1EB7C3
0x1eb7a9  ldarg.1
0x1eb7aa  ldloc.s  6
0x1eb7ac  callvirt instance object Microsoft.ReportingServices.ReportIntermediateFormat.RecordField::get_FieldValue()
0x1eb7b1  ldloc.s  6
0x1eb7b3  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.RecordField::get_IsAggregationField()
0x1eb7b8  ldloc.s  5
0x1eb7ba  newobj   instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldImpl::.ctor(class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl reportOM, object value, bool isAggregationField, class Microsoft.ReportingServices.ReportIntermediateFormat.Field fieldDef)
0x1eb7bf  stloc.s  4
0x1eb7c1  br.s     loc_1EB820
0x1eb7c3  ldloc.s  4
0x1eb7c5  ldloc.s  6
0x1eb7c7  callvirt instance object Microsoft.ReportingServices.ReportIntermediateFormat.RecordField::get_FieldValue()
0x1eb7cc  ldloc.s  6
0x1eb7ce  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.RecordField::get_IsAggregationField()
0x1eb7d3  ldc.i4.0
0x1eb7d4  ldnull
0x1eb7d5  callvirt instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldImpl::UpdateValue(object value, bool isAggregationField, valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus status, string exceptionMessage)
0x1eb7da  br.s     loc_1EB820
0x1eb7dc  ldarg.3
0x1eb7dd  brfalse.s loc_1EB7E3
0x1eb7df  ldloc.s  4
0x1eb7e1  brtrue.s loc_1EB803
0x1eb7e3  ldarg.1
0x1eb7e4  ldloc.s  6
0x1eb7e6  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus Microsoft.ReportingServices.ReportIntermediateFormat.RecordField::get_FieldStatus()
0x1eb7eb  ldloc.s  6
0x1eb7ed  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus Microsoft.ReportingServices.ReportIntermediateFormat.RecordField::get_FieldStatus()
0x1eb7f2  ldnull
0x1eb7f3  call     string Microsoft.ReportingServices.ReportProcessing.ReportRuntime::GetErrorName(valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus status, string exceptionMessage)
0x1eb7f8  ldloc.s  5
0x1eb7fa  newobj   instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldImpl::.ctor(class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl reportOM, valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus status, string exceptionMessage, class Microsoft.ReportingServices.ReportIntermediateFormat.Field fieldDef)
0x1eb7ff  stloc.s  4
0x1eb801  br.s     loc_1EB820
0x1eb803  ldloc.s  4
0x1eb805  ldnull
0x1eb806  ldc.i4.0
0x1eb807  ldloc.s  6
0x1eb809  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus Microsoft.ReportingServices.ReportIntermediateFormat.RecordField::get_FieldStatus()
0x1eb80e  ldloc.s  6
0x1eb810  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus Microsoft.ReportingServices.ReportIntermediateFormat.RecordField::get_FieldStatus()
0x1eb815  ldnull
0x1eb816  call     string Microsoft.ReportingServices.ReportProcessing.ReportRuntime::GetErrorName(valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus status, string exceptionMessage)
0x1eb81b  callvirt instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldImpl::UpdateValue(object value, bool isAggregationField, valuetype Microsoft.ReportingServices.ReportProcessing.DataFieldStatus status, string exceptionMessage)
0x1eb820  ldloc.s  6
0x1eb822  brfalse.s loc_1EB87B
0x1eb824  ldloc.0
0x1eb825  brfalse.s loc_1EB87B
0x1eb827  ldloc.0
0x1eb828  ldloc.1
0x1eb829  ldelem.ref
0x1eb82a  stloc.s  7
0x1eb82c  ldloc.s  7
0x1eb82e  brfalse.s loc_1EB87B
0x1eb830  ldloc.s  7
0x1eb832  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.FieldInfo::get_PropertyCount()
0x1eb837  brfalse.s loc_1EB87B
0x1eb839  ldloc.s  6
0x1eb83b  callvirt instance class [mscorlib]System.Collections.Generic.List`1<object> Microsoft.ReportingServices.ReportIntermediateFormat.RecordField::get_FieldPropertyValues()
0x1eb840  brfalse.s loc_1EB87B
0x1eb842  ldc.i4.0
0x1eb843  stloc.s  8
0x1eb845  br.s     loc_1EB870
0x1eb847  ldloc.s  4
0x1eb849  ldloc.s  7
0x1eb84b  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportIntermediateFormat.FieldInfo::get_PropertyNames()
0x1eb850  ldloc.s  8
0x1eb852  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x1eb857  ldloc.s  6
0x1eb859  callvirt instance class [mscorlib]System.Collections.Generic.List`1<object> Microsoft.ReportingServices.ReportIntermediateFormat.RecordField::get_FieldPropertyValues()
0x1eb85e  ldloc.s  8
0x1eb860  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0x1eb865  callvirt instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldImpl::SetProperty(string propertyName, object propertyValue)
0x1eb86a  ldloc.s  8
0x1eb86c  ldc.i4.1
0x1eb86d  add
0x1eb86e  stloc.s  8
0x1eb870  ldloc.s  8
0x1eb872  ldloc.s  7
0x1eb874  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.FieldInfo::get_PropertyCount()
0x1eb879  blt.s    loc_1EB847
0x1eb87b  ldarg.0
0x1eb87c  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_fields
0x1eb881  ldloc.1
0x1eb882  ldloc.s  4
0x1eb884  callvirt instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::set_Item(int32 index, class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldImpl value)
0x1eb889  ldloc.1
0x1eb88a  ldc.i4.1
0x1eb88b  add
0x1eb88c  stloc.1
0x1eb88d  ldloc.1
0x1eb88e  ldloc.3
0x1eb88f  blt      loc_1EB73B
0x1eb894  ldloc.1
0x1eb895  ldloc.2
0x1eb896  bge      loc_1EB936
0x1eb89b  ldarg.3
0x1eb89c  brtrue   loc_1EB932
0x1eb8a1  ldarg.1
0x1eb8a2  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl::get_OdpContext()
0x1eb8a7  callvirt instance class Microsoft.ReportingServices.RdlExpressions.ReportRuntime Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ReportRuntime()
0x1eb8ac  callvirt instance class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportExprHost Microsoft.ReportingServices.RdlExpressions.ReportRuntime::get_ReportExprHost()
0x1eb8b1  brfalse.s loc_1EB932
0x1eb8b3  ldarg.0
0x1eb8b4  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_dataSet
0x1eb8b9  ldarg.1
0x1eb8ba  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl::get_OdpContext()
0x1eb8bf  callvirt instance class Microsoft.ReportingServices.RdlExpressions.ReportRuntime Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ReportRuntime()
0x1eb8c4  callvirt instance class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportExprHost Microsoft.ReportingServices.RdlExpressions.ReportRuntime::get_ReportExprHost()
0x1eb8c9  ldarg.1
0x1eb8ca  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore::SetExprHost(class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportExprHost reportExprHost, class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl reportObjectModel)
0x1eb8cf  br.s     loc_1EB932
0x1eb8d1  ldarg.0
0x1eb8d2  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_dataSet
0x1eb8d7  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Field> Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore::get_Fields()
0x1eb8dc  ldloc.1
0x1eb8dd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.Field>::get_Item(!!T0)
0x1eb8e2  stloc.s  9
0x1eb8e4  ldarg.3
0x1eb8e5  brtrue.s loc_1EB8EA
0x1eb8e7  ldnull
0x1eb8e8  br.s     loc_1EB8F6
0x1eb8ea  ldarg.0
0x1eb8eb  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_fields
0x1eb8f0  ldloc.1
0x1eb8f1  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::GetFieldByIndex(int32 index)
0x1eb8f6  stloc.s  0xA
0x1eb8f8  ldarg.3
0x1eb8f9  brfalse.s loc_1EB91C
0x1eb8fb  ldloc.s  0xA
0x1eb8fd  brfalse.s loc_1EB91C
0x1eb8ff  ldloc.s  0xA
0x1eb901  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldImpl::ResetCalculatedField()
0x1eb906  brtrue.s loc_1EB92E
0x1eb908  ldarg.0
0x1eb909  ldarg.1
0x1eb90a  ldarg.s  6
0x1eb90c  ldarg.0
0x1eb90d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_dataSet
0x1eb912  ldloc.1
0x1eb913  ldloc.s  9
0x1eb915  call     instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::CreateAndInitializeCalculatedFieldWrapper(class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl reportOM, bool readerExtensionsSupported, class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore dataSet, int32 fieldIndex, class Microsoft.ReportingServices.ReportIntermediateFormat.Field fieldDef)
0x1eb91a  br.s     loc_1EB92E
0x1eb91c  ldarg.0
0x1eb91d  ldarg.1
0x1eb91e  ldarg.s  6
0x1eb920  ldarg.0
0x1eb921  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::m_dataSet
0x1eb926  ldloc.1
0x1eb927  ldloc.s  9
0x1eb929  call     instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsContext::CreateAndInitializeCalculatedFieldWrapper(class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl reportOM, bool readerExtensionsSupported, class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore dataSet, int32 fieldIndex, class Microsoft.ReportingServices.ReportIntermediateFormat.Field fieldDef)
0x1eb92e  ldloc.1
0x1eb92f  ldc.i4.1
0x1eb930  add
0x1eb931  stloc.1
0x1eb932  ldloc.1
0x1eb933  ldloc.2
0x1eb934  blt.s    loc_1EB8D1
0x1eb936  ret
```
