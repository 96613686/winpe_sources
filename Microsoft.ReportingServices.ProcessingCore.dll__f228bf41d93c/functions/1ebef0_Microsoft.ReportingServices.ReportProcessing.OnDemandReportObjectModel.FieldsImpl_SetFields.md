# Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::SetFields

- ea: `0x1ebef0`
- end: `0x1ebfe3`
- name: `Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::SetFields`
- size: `243`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1eb520`
- `0x1ebff0`
- `0x216170`

## callees

- `0x1ebe60`
- `0x1ebef0`
- `0x1ec210`
- `0x1ec650`

## string_xrefs

- `0x1ebf84`: `Wrong number of fields during ReportOM update.  Usually this means the data set is wrong.  Expected: {0}.  Actual: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1ebef0  ldarg.0
0x1ebef1  ldfld    bool Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::m_referenced
0x1ebef6  brtrue.s loc_1EBF0E
0x1ebef8  ldarg.2
0x1ebef9  ldsfld   int64 Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.DataFieldRow::UnInitializedStreamOffset
0x1ebefe  beq.s    loc_1EBF0E
0x1ebf00  ldarg.0
0x1ebf01  ldfld    int64 Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::m_streamOffset
0x1ebf06  ldarg.2
0x1ebf07  ceq
0x1ebf09  ldc.i4.0
0x1ebf0a  ceq
0x1ebf0c  br.s     loc_1EBF0F
0x1ebf0e  ldc.i4.1
0x1ebf0f  stloc.0
0x1ebf10  ldarg.0
0x1ebf11  ldarg.2
0x1ebf12  call     instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::NewRow(int64 streamOffset)
0x1ebf17  ldarg.0
0x1ebf18  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldImpl[] Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::m_collection
0x1ebf1d  brtrue.s loc_1EBF2F
0x1ebf1f  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1ebf24  ldc.i4.0
0x1ebf25  ldstr    aInvalidFieldsi// "Invalid FieldsImpl.  m_collection shoul"...
0x1ebf2a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1ebf2f  ldarg.1
0x1ebf30  brtrue.s loc_1EBF70
0x1ebf32  ldc.i4.0
0x1ebf33  stloc.1
0x1ebf34  br.s     loc_1EBF66
0x1ebf36  ldarg.0
0x1ebf37  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldImpl[] Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::m_collection
0x1ebf3c  ldloc.1
0x1ebf3d  ldelem.ref
0x1ebf3e  stloc.2
0x1ebf3f  ldloc.2
0x1ebf40  brfalse.s loc_1EBF4A
0x1ebf42  ldloc.2
0x1ebf43  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Field Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldImpl::get_FieldDef()
0x1ebf48  br.s     loc_1EBF4B
0x1ebf4a  ldnull
0x1ebf4b  stloc.3
0x1ebf4c  ldarg.0
0x1ebf4d  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldImpl[] Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::m_collection
0x1ebf52  ldloc.1
0x1ebf53  ldarg.0
0x1ebf54  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::m_reportOM
0x1ebf59  ldnull
0x1ebf5a  ldc.i4.0
0x1ebf5b  ldloc.3
0x1ebf5c  newobj   instance void Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldImpl::.ctor(class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl reportOM, object value, bool isAggregationField, class Microsoft.ReportingServices.ReportIntermediateFormat.Field fieldDef)
0x1ebf61  stelem.ref
0x1ebf62  ldloc.1
0x1ebf63  ldc.i4.1
0x1ebf64  add
0x1ebf65  stloc.1
0x1ebf66  ldloc.1
0x1ebf67  ldarg.0
0x1ebf68  ldfld    int32 Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::m_count
0x1ebf6d  blt.s    loc_1EBF36
0x1ebf6f  ret
0x1ebf70  ldloc.0
0x1ebf71  brfalse.s loc_1EBFE2
0x1ebf73  ldarg.1
0x1ebf74  ldlen
0x1ebf75  conv.i4
0x1ebf76  ldarg.0
0x1ebf77  ldfld    int32 Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::m_count
0x1ebf7c  beq.s    loc_1EBFAD
0x1ebf7e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1ebf83  ldc.i4.0
0x1ebf84  ldstr    aWrongNumberOfF// "Wrong number of fields during ReportOM "...
0x1ebf89  ldc.i4.2
0x1ebf8a  newarr   [mscorlib]System.Object
0x1ebf8f  dup
0x1ebf90  ldc.i4.0
0x1ebf91  ldarg.0
0x1ebf92  ldfld    int32 Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::m_count
0x1ebf97  box      [mscorlib]System.Int32
0x1ebf9c  stelem.ref
0x1ebf9d  dup
0x1ebf9e  ldc.i4.1
0x1ebf9f  ldarg.1
0x1ebfa0  ldlen
0x1ebfa1  conv.i4
0x1ebfa2  box      [mscorlib]System.Int32
0x1ebfa7  stelem.ref
0x1ebfa8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string, object[])
0x1ebfad  ldc.i4.0
0x1ebfae  stloc.s  4
0x1ebfb0  br.s     loc_1EBFC5
0x1ebfb2  ldarg.0
0x1ebfb3  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldImpl[] Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::m_collection
0x1ebfb8  ldloc.s  4
0x1ebfba  ldarg.1
0x1ebfbb  ldloc.s  4
0x1ebfbd  ldelem.ref
0x1ebfbe  stelem.ref
0x1ebfbf  ldloc.s  4
0x1ebfc1  ldc.i4.1
0x1ebfc2  add
0x1ebfc3  stloc.s  4
0x1ebfc5  ldloc.s  4
0x1ebfc7  ldarg.0
0x1ebfc8  ldfld    int32 Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::m_count
0x1ebfcd  blt.s    loc_1EBFB2
0x1ebfcf  ldarg.0
0x1ebfd0  ldc.i4.0
0x1ebfd1  stfld    bool Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::m_isAggregateRow
0x1ebfd6  ldarg.0
0x1ebfd7  ldarg.0
0x1ebfd8  ldfld    int32 Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::m_aggregationFieldCountForDetailRow
0x1ebfdd  stfld    int32 Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.FieldsImpl::m_aggregationFieldCount
0x1ebfe2  ret
```
