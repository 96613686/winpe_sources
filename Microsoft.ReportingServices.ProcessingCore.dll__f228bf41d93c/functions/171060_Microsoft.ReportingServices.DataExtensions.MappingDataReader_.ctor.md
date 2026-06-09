# Microsoft.ReportingServices.DataExtensions.MappingDataReader::.ctor

- ea: `0x171060`
- end: `0x171221`
- name: `Microsoft.ReportingServices.DataExtensions.MappingDataReader::.ctor`
- size: `449`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1f3790`
- `0x25b8f0`

## callees

- `0x171060`
- `0x175e50`

## string_xrefs

- `0x17107b`: `The source data reader is null. Cannot read results.`
- `0x1710f9`: `The array of field names is null. Aliases will map positionally to the data reader fields.`
- `0x171157`: `The data reader does not have any fields.`
- `0x171216`: `Mapping data reader successfully initialized.`

## pseudocode

```c

```

## disassembly

```asm
0x171060  ldarg.0
0x171061  call     instance void [mscorlib]System.Object::.ctor()
0x171066  ldarg.2
0x171067  brtrue.s loc_17109A
0x171069  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x17106e  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x171073  brfalse.s loc_171085
0x171075  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x17107a  ldc.i4.1
0x17107b  ldstr    aTheSourceDataR// "The source data reader is null. Cannot "...
0x171080  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x171085  ldc.i4   0xAB
0x17108a  ldc.i4.1
0x17108b  newarr   [mscorlib]System.Object
0x171090  dup
0x171091  ldc.i4.0
0x171092  ldarg.1
0x171093  stelem.ref
0x171094  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, object[] arguments)
0x171099  throw
0x17109a  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x17109f  ldarg.3
0x1710a0  ldnull
0x1710a1  cgt.un
0x1710a3  ldstr    aNullAliases// "(null != aliases)"
0x1710a8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1710ad  ldarg.0
0x1710ae  ldarg.1
0x1710af  stfld    string Microsoft.ReportingServices.DataExtensions.MappingDataReader::m_dataSetName
0x1710b4  ldarg.0
0x1710b5  ldarg.2
0x1710b6  stfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataReader Microsoft.ReportingServices.DataExtensions.MappingDataReader::m_dataReader
0x1710bb  ldarg.0
0x1710bc  ldarg.s  4
0x1710be  stfld    string[] Microsoft.ReportingServices.DataExtensions.MappingDataReader::m_fieldNames
0x1710c3  ldarg.0
0x1710c4  ldarg.s  5
0x1710c6  stfld    class Microsoft.ReportingServices.OnDemandProcessing.DataSourceErrorInspector Microsoft.ReportingServices.DataExtensions.MappingDataReader::m_errorInspector
0x1710cb  ldarg.0
0x1710cc  ldarg.2
0x1710cd  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataReaderExtension
0x1710d2  stfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataReaderExtension Microsoft.ReportingServices.DataExtensions.MappingDataReader::m_dataReaderExtension
0x1710d7  ldarg.0
0x1710d8  ldarg.2
0x1710d9  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataReaderFieldProperties
0x1710de  stfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataReaderFieldProperties Microsoft.ReportingServices.DataExtensions.MappingDataReader::m_dataFieldProperties
0x1710e3  ldarg.s  4
0x1710e5  brtrue.s loc_17111B
0x1710e7  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1710ec  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x1710f1  brfalse.s loc_171103
0x1710f3  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1710f8  ldc.i4.3
0x1710f9  ldstr    aTheArrayOfFiel// "The array of field names is null. Alias"...
0x1710fe  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x171103  ldc.i4.0
0x171104  stloc.0
0x171105  br.s     loc_171114
0x171107  ldarg.0
0x171108  ldfld    int32[] Microsoft.ReportingServices.DataExtensions.MappingDataReader::m_aliasIndexToFieldIndex
0x17110d  ldloc.0
0x17110e  ldloc.0
0x17110f  stelem.i4
0x171110  ldloc.0
0x171111  ldc.i4.1
0x171112  add
0x171113  stloc.0
0x171114  ldloc.0
0x171115  ldarg.3
0x171116  ldlen
0x171117  conv.i4
0x171118  blt.s    loc_171107
0x17111a  ret
0x17111b  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x171120  ldarg.3
0x171121  ldlen
0x171122  conv.i4
0x171123  ldarg.s  4
0x171125  ldlen
0x171126  conv.i4
0x171127  ceq
0x171129  ldstr    aAliasesLengthF// " (aliases.Length == fieldNames.Length)"
0x17112e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x171133  ldarg.0
0x171134  ldarg.3
0x171135  ldlen
0x171136  conv.i4
0x171137  newarr   [mscorlib]System.Int32
0x17113c  stfld    int32[] Microsoft.ReportingServices.DataExtensions.MappingDataReader::m_aliasIndexToFieldIndex
0x171141  ldarg.s  4
0x171143  brtrue.s loc_171179
0x171145  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x17114a  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x17114f  brfalse.s loc_171161
0x171151  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x171156  ldc.i4.2
0x171157  ldstr    aTheDataReaderD// "The data reader does not have any field"...
0x17115c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x171161  ldc.i4.0
0x171162  stloc.1
0x171163  br.s     loc_171172
0x171165  ldarg.0
0x171166  ldfld    int32[] Microsoft.ReportingServices.DataExtensions.MappingDataReader::m_aliasIndexToFieldIndex
0x17116b  ldloc.1
0x17116c  ldc.i4.m1
0x17116d  stelem.i4
0x17116e  ldloc.1
0x17116f  ldc.i4.1
0x171170  add
0x171171  stloc.1
0x171172  ldloc.1
0x171173  ldarg.3
0x171174  ldlen
0x171175  conv.i4
0x171176  blt.s    loc_171165
0x171178  ret
0x171179  ldc.i4.0
0x17117a  stloc.2
0x17117b  br.s     loc_1711FB
0x17117d  ldarg.s  4
0x17117f  ldloc.2
0x171180  ldelem.ref
0x171181  stloc.3
0x171182  ldloc.3
0x171183  brfalse.s loc_1711E3
0x171185  ldarg.0
0x171186  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataReader Microsoft.ReportingServices.DataExtensions.MappingDataReader::m_dataReader
0x17118b  ldloc.3
0x17118c  callvirt instance int32 [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataReader::GetOrdinal(string)
0x171191  stloc.s  4
0x171193  leave.s  loc_1711D7
0x171195  pop
0x171196  rethrow
0x171198  stloc.s  5
0x17119a  ldloc.s  5
0x17119c  call     bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Common.AsynchronousExceptionDetection::IsStoppingException(class [mscorlib]System.Exception)
0x1711a1  brfalse.s loc_1711A5
0x1711a3  rethrow
0x1711a5  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1711aa  ldc.i4.2
0x1711ab  ldstr    aAnExceptionOcc_1// "An exception occurred while trying to m"...
0x1711b0  ldc.i4.3
0x1711b1  newarr   [mscorlib]System.Object
0x1711b6  dup
0x1711b7  ldc.i4.0
0x1711b8  ldarg.3
0x1711b9  ldloc.2
0x1711ba  ldelem.ref
0x1711bb  stelem.ref
0x1711bc  dup
0x1711bd  ldc.i4.1
0x1711be  ldarg.s  4
0x1711c0  ldloc.2
0x1711c1  ldelem.ref
0x1711c2  stelem.ref
0x1711c3  dup
0x1711c4  ldc.i4.2
0x1711c5  ldloc.s  5
0x1711c7  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1711cc  stelem.ref
0x1711cd  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1711d2  ldc.i4.m1
0x1711d3  stloc.s  4
0x1711d5  leave.s  loc_1711D7
0x1711d7  ldarg.0
0x1711d8  ldfld    int32[] Microsoft.ReportingServices.DataExtensions.MappingDataReader::m_aliasIndexToFieldIndex
0x1711dd  ldloc.2
0x1711de  ldloc.s  4
0x1711e0  stelem.i4
0x1711e1  br.s     loc_1711F7
0x1711e3  ldarg.0
0x1711e4  ldfld    int32[] Microsoft.ReportingServices.DataExtensions.MappingDataReader::m_aliasIndexToFieldIndex
0x1711e9  ldloc.2
0x1711ea  ldc.i4.m1
0x1711eb  stelem.i4
0x1711ec  ldarg.0
0x1711ed  ldfld    string[] Microsoft.ReportingServices.DataExtensions.MappingDataReader::m_fieldNames
0x1711f2  ldloc.2
0x1711f3  ldarg.3
0x1711f4  ldloc.2
0x1711f5  ldelem.ref
0x1711f6  stelem.ref
0x1711f7  ldloc.2
0x1711f8  ldc.i4.1
0x1711f9  add
0x1711fa  stloc.2
0x1711fb  ldloc.2
0x1711fc  ldarg.3
0x1711fd  ldlen
0x1711fe  conv.i4
0x1711ff  blt      loc_17117D
0x171204  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x171209  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x17120e  brfalse.s loc_171220
0x171210  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x171215  ldc.i4.4
0x171216  ldstr    aMappingDataRea// "Mapping data reader successfully initia"...
0x17121b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x171220  ret
```
