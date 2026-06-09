# Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::AggregateDataShapeMetrics

- ea: `0xaaa0`
- end: `0xade3`
- name: `Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::AggregateDataShapeMetrics`
- size: `835`
- prototype: ``
- caller_count: `0`
- callee_count: `38`
- tags: `service_task, broker_com_uri`

## callees

- `0xa950`
- `0xa9c0`
- `0xa9e0`
- `0xaa00`
- `0xaa20`
- `0xaaa0`
- `0xadf0`
- `0x12b60`
- `0x12bb0`
- `0x12bd0`
- `0x12c20`
- `0x12ec0`
- `0x12f00`
- `0x12fb0`
- `0x13140`
- `0x13170`
- `0x131a0`
- `0x131d0`
- `0x13200`
- `0x13210`
- `0x13220`
- `0x13230`
- `0x13240`
- `0x13350`
- `0x13360`
- `0x13370`
- `0x13390`
- `0x133a0`
- `0x133c0`
- `0x133d0`
- `0x134d0`
- `0x135f0`
- `0x13600`
- `0x13610`
- `0x13630`
- `0x13640`
- `0x13660`
- `0x13670`

## pseudocode

```c

```

## disassembly

```asm
0xaaa0  ldarg.0
0xaaa1  ldfld    class Microsoft.ReportingServices.Diagnostics.Internal.AdditionalInfo Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::m_additionalInfo
0xaaa6  brfalse.s loc_AAB5
0xaaa8  ldarg.0
0xaaa9  ldfld    class Microsoft.ReportingServices.Diagnostics.Internal.AdditionalInfo Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::m_additionalInfo
0xaaae  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.Internal.DataShape> Microsoft.ReportingServices.Diagnostics.Internal.AdditionalInfo::get_DataShapes()
0xaab3  brtrue.s loc_AAB6
0xaab5  ret
0xaab6  ldloca.s 0
0xaab8  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0xaabe  ldloca.s 1
0xaac0  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0xaac6  ldloca.s 2
0xaac8  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0xaace  ldloca.s 3
0xaad0  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0xaad6  ldloca.s 4
0xaad8  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0xaade  ldloca.s 5
0xaae0  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0xaae6  ldloca.s 6
0xaae8  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0xaaee  ldloca.s 7
0xaaf0  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0xaaf6  ldloca.s 8
0xaaf8  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0xaafe  ldloca.s 9
0xab00  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0xab06  ldloca.s 0xA
0xab08  initobj  valuetype [mscorlib]System.Nullable`1<int64>
0xab0e  ldarg.0
0xab0f  ldfld    class Microsoft.ReportingServices.Diagnostics.Internal.AdditionalInfo Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::m_additionalInfo
0xab14  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.Internal.DataShape> Microsoft.ReportingServices.Diagnostics.Internal.AdditionalInfo::get_DataShapes()
0xab19  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.Internal.DataShape>::GetEnumerator()
0xab1e  stloc.s  0xB
0xab20  br       loc_ACC1
0xab25  ldloca.s 0xB
0xab27  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Diagnostics.Internal.DataShape>::get_Current()
0xab2c  stloc.s  0xC
0xab2e  ldarg.0
0xab2f  ldloc.s  0xC
0xab31  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Diagnostics.Internal.DataShape::get_TimeQueryTranslation()
0xab36  ldloca.s 0
0xab38  call     instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::AggregateValue(valuetype [mscorlib]System.Nullable`1<int64> from, valuetype [mscorlib]System.Nullable`1<int64>& to)
0xab3d  ldarg.0
0xab3e  ldloc.s  0xC
0xab40  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Diagnostics.Internal.DataShape::get_TimeQueryTranslation()
0xab45  ldloca.s 1
0xab47  call     instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::AggregateValue(valuetype [mscorlib]System.Nullable`1<int64> from, valuetype [mscorlib]System.Nullable`1<int64>& to)
0xab4c  ldarg.0
0xab4d  ldloc.s  0xC
0xab4f  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Diagnostics.Internal.DataShape::get_TimeProcessing()
0xab54  ldloca.s 1
0xab56  call     instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::AggregateValue(valuetype [mscorlib]System.Nullable`1<int64> from, valuetype [mscorlib]System.Nullable`1<int64>& to)
0xab5b  ldarg.0
0xab5c  ldloc.s  0xC
0xab5e  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Diagnostics.Internal.DataShape::get_TimeRendering()
0xab63  ldloca.s 2
0xab65  call     instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::AggregateValue(valuetype [mscorlib]System.Nullable`1<int64> from, valuetype [mscorlib]System.Nullable`1<int64>& to)
0xab6a  ldarg.0
0xab6b  ldloc.s  0xC
0xab6d  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Diagnostics.Internal.DataShape::get_TimeDataRetrieval()
0xab72  ldloca.s 3
0xab74  call     instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::AggregateValue(valuetype [mscorlib]System.Nullable`1<int64> from, valuetype [mscorlib]System.Nullable`1<int64>& to)
0xab79  ldloc.s  0xC
0xab7b  callvirt instance class Microsoft.ReportingServices.Diagnostics.Internal.EstimatedMemoryUsageKBCategory Microsoft.ReportingServices.Diagnostics.Internal.DataShape::get_EstimatedMemoryUsageKB()
0xab80  brfalse.s loc_ABBE
0xab82  ldarg.0
0xab83  ldloc.s  0xC
0xab85  callvirt instance class Microsoft.ReportingServices.Diagnostics.Internal.EstimatedMemoryUsageKBCategory Microsoft.ReportingServices.Diagnostics.Internal.DataShape::get_EstimatedMemoryUsageKB()
0xab8a  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Diagnostics.Internal.EstimatedMemoryUsageKBCategory::get_Pagination()
0xab8f  ldloca.s 5
0xab91  call     instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::AggregateValue(valuetype [mscorlib]System.Nullable`1<int64> from, valuetype [mscorlib]System.Nullable`1<int64>& to)
0xab96  ldarg.0
0xab97  ldloc.s  0xC
0xab99  callvirt instance class Microsoft.ReportingServices.Diagnostics.Internal.EstimatedMemoryUsageKBCategory Microsoft.ReportingServices.Diagnostics.Internal.DataShape::get_EstimatedMemoryUsageKB()
0xab9e  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Diagnostics.Internal.EstimatedMemoryUsageKBCategory::get_Processing()
0xaba3  ldloca.s 6
0xaba5  call     instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::AggregateValue(valuetype [mscorlib]System.Nullable`1<int64> from, valuetype [mscorlib]System.Nullable`1<int64>& to)
0xabaa  ldarg.0
0xabab  ldloc.s  0xC
0xabad  callvirt instance class Microsoft.ReportingServices.Diagnostics.Internal.EstimatedMemoryUsageKBCategory Microsoft.ReportingServices.Diagnostics.Internal.DataShape::get_EstimatedMemoryUsageKB()
0xabb2  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Diagnostics.Internal.EstimatedMemoryUsageKBCategory::get_Rendering()
0xabb7  ldloca.s 7
0xabb9  call     instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::AggregateValue(valuetype [mscorlib]System.Nullable`1<int64> from, valuetype [mscorlib]System.Nullable`1<int64>& to)
0xabbe  ldloc.s  0xC
0xabc0  callvirt instance class Microsoft.ReportingServices.Diagnostics.Internal.ScaleTimeCategory Microsoft.ReportingServices.Diagnostics.Internal.DataShape::get_ScalabilityTime()
0xabc5  brfalse.s loc_AC03
0xabc7  ldarg.0
0xabc8  ldloc.s  0xC
0xabca  callvirt instance class Microsoft.ReportingServices.Diagnostics.Internal.ScaleTimeCategory Microsoft.ReportingServices.Diagnostics.Internal.DataShape::get_ScalabilityTime()
0xabcf  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Diagnostics.Internal.ScaleTimeCategory::get_Pagination()
0xabd4  ldloca.s 8
0xabd6  call     instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::AggregateValue(valuetype [mscorlib]System.Nullable`1<int64> from, valuetype [mscorlib]System.Nullable`1<int64>& to)
0xabdb  ldarg.0
0xabdc  ldloc.s  0xC
0xabde  callvirt instance class Microsoft.ReportingServices.Diagnostics.Internal.ScaleTimeCategory Microsoft.ReportingServices.Diagnostics.Internal.DataShape::get_ScalabilityTime()
0xabe3  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Diagnostics.Internal.ScaleTimeCategory::get_Processing()
0xabe8  ldloca.s 9
0xabea  call     instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::AggregateValue(valuetype [mscorlib]System.Nullable`1<int64> from, valuetype [mscorlib]System.Nullable`1<int64>& to)
0xabef  ldarg.0
0xabf0  ldloc.s  0xC
0xabf2  callvirt instance class Microsoft.ReportingServices.Diagnostics.Internal.ScaleTimeCategory Microsoft.ReportingServices.Diagnostics.Internal.DataShape::get_ScalabilityTime()
0xabf7  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Diagnostics.Internal.ScaleTimeCategory::get_Rendering()
0xabfc  ldloca.s 0xA
0xabfe  call     instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::AggregateValue(valuetype [mscorlib]System.Nullable`1<int64> from, valuetype [mscorlib]System.Nullable`1<int64>& to)
0xac03  ldarg.0
0xac04  call     instance valuetype Microsoft.ReportingServices.Diagnostics.ExecutionLogLevel Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::get_ExecutionLogLevel()
0xac09  ldc.i4.1
0xac0a  beq.s    loc_AC1C
0xac0c  ldloc.s  0xC
0xac0e  ldnull
0xac0f  callvirt instance void Microsoft.ReportingServices.Diagnostics.Internal.DataShape::set_EstimatedMemoryUsageKB(class Microsoft.ReportingServices.Diagnostics.Internal.EstimatedMemoryUsageKBCategory value)
0xac14  ldloc.s  0xC
0xac16  ldnull
0xac17  callvirt instance void Microsoft.ReportingServices.Diagnostics.Internal.DataShape::set_ScalabilityTime(class Microsoft.ReportingServices.Diagnostics.Internal.ScaleTimeCategory value)
0xac1c  ldloc.s  0xC
0xac1e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.Internal.Connection> Microsoft.ReportingServices.Diagnostics.Internal.DataShape::get_Connections()
0xac23  brfalse  loc_ACC1
0xac28  ldloc.s  0xC
0xac2a  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.Internal.Connection> Microsoft.ReportingServices.Diagnostics.Internal.DataShape::get_Connections()
0xac2f  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.Internal.Connection>::GetEnumerator()
0xac34  stloc.s  0xD
0xac36  br.s     loc_ACA8
0xac38  ldloca.s 0xD
0xac3a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Diagnostics.Internal.Connection>::get_Current()
0xac3f  stloc.s  0xE
0xac41  ldloc.s  0xE
0xac43  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.Internal.DataSet> Microsoft.ReportingServices.Diagnostics.Internal.Connection::get_DataSets()
0xac48  brfalse.s loc_AC8B
0xac4a  ldloc.s  0xE
0xac4c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.Internal.DataSet> Microsoft.ReportingServices.Diagnostics.Internal.Connection::get_DataSets()
0xac51  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Diagnostics.Internal.DataSet>::GetEnumerator()
0xac56  stloc.s  0xF
0xac58  br.s     loc_AC72
0xac5a  ldloca.s 0xF
0xac5c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Diagnostics.Internal.DataSet>::get_Current()
0xac61  stloc.s  0x10
0xac63  ldarg.0
0xac64  ldloc.s  0x10
0xac66  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Diagnostics.Internal.DataSet::get_RowsRead()
0xac6b  ldloca.s 4
0xac6d  call     instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::AggregateValue(valuetype [mscorlib]System.Nullable`1<int64> from, valuetype [mscorlib]System.Nullable`1<int64>& to)
0xac72  ldloca.s 0xF
0xac74  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Diagnostics.Internal.DataSet>::MoveNext()
0xac79  brtrue.s loc_AC5A
0xac7b  leave.s  loc_AC8B
0xac7d  ldloca.s 0xF
0xac7f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Diagnostics.Internal.DataSet>
0xac85  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xac8a  endfinally
0xac8b  ldloc.s  0xE
0xac8d  callvirt instance class Microsoft.ReportingServices.Diagnostics.Internal.ModelMetadata Microsoft.ReportingServices.Diagnostics.Internal.Connection::get_ModelMetadata()
0xac92  brfalse.s loc_ACA8
0xac94  ldarg.0
0xac95  ldloc.s  0xE
0xac97  callvirt instance class Microsoft.ReportingServices.Diagnostics.Internal.ModelMetadata Microsoft.ReportingServices.Diagnostics.Internal.Connection::get_ModelMetadata()
0xac9c  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.ReportingServices.Diagnostics.Internal.ModelMetadata::get_TotalTimeDataRetrieval()
0xaca1  ldloca.s 3
0xaca3  call     instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::AggregateValue(valuetype [mscorlib]System.Nullable`1<int64> from, valuetype [mscorlib]System.Nullable`1<int64>& to)
0xaca8  ldloca.s 0xD
0xacaa  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Diagnostics.Internal.Connection>::MoveNext()
0xacaf  brtrue.s loc_AC38
0xacb1  leave.s  loc_ACC1
0xacb3  ldloca.s 0xD
0xacb5  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Diagnostics.Internal.Connection>
0xacbb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xacc0  endfinally
0xacc1  ldloca.s 0xB
0xacc3  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Diagnostics.Internal.DataShape>::MoveNext()
0xacc8  brtrue   loc_AB25
0xaccd  leave.s  loc_ACDD
0xaccf  ldloca.s 0xB
0xacd1  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Diagnostics.Internal.DataShape>
0xacd7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xacdc  endfinally
0xacdd  ldloca.s 0
0xacdf  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0xace4  brfalse.s loc_ACF2
0xace6  ldarg.0
0xace7  ldfld    class Microsoft.ReportingServices.Diagnostics.Internal.AdditionalInfo Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::m_additionalInfo
0xacec  ldloc.0
0xaced  callvirt instance void Microsoft.ReportingServices.Diagnostics.Internal.AdditionalInfo::set_TimeQueryTranslation(valuetype [mscorlib]System.Nullable`1<int64> value)
0xacf2  ldloca.s 1
0xacf4  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0xacf9  brfalse.s loc_AD0E
0xacfb  ldarg.0
0xacfc  ldloca.s 1
0xacfe  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0xad03  conv.r8
0xad04  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMilliseconds(float64)
0xad09  call     instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::set_ProcessingTime(valuetype [mscorlib]System.TimeSpan value)
0xad0e  ldloca.s 2
0xad10  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0xad15  brfalse.s loc_AD2A
0xad17  ldarg.0
0xad18  ldloca.s 2
0xad1a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0xad1f  conv.r8
0xad20  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMilliseconds(float64)
0xad25  call     instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::set_RenderingTime(valuetype [mscorlib]System.TimeSpan value)
0xad2a  ldloca.s 3
0xad2c  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0xad31  brfalse.s loc_AD46
0xad33  ldarg.0
0xad34  ldloca.s 3
0xad36  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0xad3b  conv.r8
0xad3c  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMilliseconds(float64)
0xad41  call     instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::set_DataRetrievalTime(valuetype [mscorlib]System.TimeSpan value)
0xad46  ldloca.s 4
0xad48  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0xad4d  brfalse.s loc_AD5C
0xad4f  ldarg.0
0xad50  ldloca.s 4
0xad52  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0xad57  call     instance void Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::set_RowCount(int64 value)
0xad5c  ldloca.s 5
0xad5e  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0xad63  brtrue.s loc_AD77
0xad65  ldloca.s 6
0xad67  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0xad6c  brtrue.s loc_AD77
0xad6e  ldloca.s 7
0xad70  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0xad75  brfalse.s loc_AD9F
0xad77  ldarg.0
0xad78  ldfld    class Microsoft.ReportingServices.Diagnostics.Internal.AdditionalInfo Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::m_additionalInfo
0xad7d  newobj   instance void Microsoft.ReportingServices.Diagnostics.Internal.EstimatedMemoryUsageKBCategory::.ctor()
0xad82  dup
0xad83  ldloc.s  5
0xad85  callvirt instance void Microsoft.ReportingServices.Diagnostics.Internal.EstimatedMemoryUsageKBCategory::set_Pagination(valuetype [mscorlib]System.Nullable`1<int64> value)
0xad8a  dup
0xad8b  ldloc.s  6
0xad8d  callvirt instance void Microsoft.ReportingServices.Diagnostics.Internal.EstimatedMemoryUsageKBCategory::set_Processing(valuetype [mscorlib]System.Nullable`1<int64> value)
0xad92  dup
0xad93  ldloc.s  7
0xad95  callvirt instance void Microsoft.ReportingServices.Diagnostics.Internal.EstimatedMemoryUsageKBCategory::set_Rendering(valuetype [mscorlib]System.Nullable`1<int64> value)
0xad9a  callvirt instance void Microsoft.ReportingServices.Diagnostics.Internal.AdditionalInfo::set_EstimatedMemoryUsageKB(class Microsoft.ReportingServices.Diagnostics.Internal.EstimatedMemoryUsageKBCategory value)
0xad9f  ldloca.s 8
0xada1  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0xada6  brtrue.s loc_ADBA
0xada8  ldloca.s 9
0xadaa  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0xadaf  brtrue.s loc_ADBA
0xadb1  ldloca.s 0xA
0xadb3  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0xadb8  brfalse.s loc_ADE2
0xadba  ldarg.0
0xadbb  ldfld    class Microsoft.ReportingServices.Diagnostics.Internal.AdditionalInfo Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::m_additionalInfo
0xadc0  newobj   instance void Microsoft.ReportingServices.Diagnostics.Internal.ScaleTimeCategory::.ctor()
0xadc5  dup
0xadc6  ldloc.s  8
0xadc8  callvirt instance void Microsoft.ReportingServices.Diagnostics.Internal.ScaleTimeCategory::set_Pagination(valuetype [mscorlib]System.Nullable`1<int64> value)
0xadcd  dup
0xadce  ldloc.s  9
0xadd0  callvirt instance void Microsoft.ReportingServices.Diagnostics.Internal.ScaleTimeCategory::set_Processing(valuetype [mscorlib]System.Nullable`1<int64> value)
0xadd5  dup
0xadd6  ldloc.s  0xA
0xadd8  callvirt instance void Microsoft.ReportingServices.Diagnostics.Internal.ScaleTimeCategory::set_Rendering(valuetype [mscorlib]System.Nullable`1<int64> value)
0xaddd  callvirt instance void Microsoft.ReportingServices.Diagnostics.Internal.AdditionalInfo::set_ScalabilityTime(class Microsoft.ReportingServices.Diagnostics.Internal.ScaleTimeCategory value)
0xade2  ret
```
