# Microsoft.ReportingServices.DataExtensions.MappingDataReader::IsAggregationField

- ea: `0x171340`
- end: `0x17138b`
- name: `Microsoft.ReportingServices.DataExtensions.MappingDataReader::IsAggregationField`
- size: `75`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1f39c0`
- `0x25ba70`

## callees

- `0x171340`
- `0x1714a0`
- `0x175de0`

## string_xrefs

- `0x17134e`: `(null != m_dataReaderExtension)`

## pseudocode

```c

```

## disassembly

```asm
0x171340  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x171345  ldarg.0
0x171346  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataReaderExtension Microsoft.ReportingServices.DataExtensions.MappingDataReader::m_dataReaderExtension
0x17134b  ldnull
0x17134c  cgt.un
0x17134e  ldstr    aNullMDatareade// "(null != m_dataReaderExtension)"
0x171353  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x171358  ldarg.0
0x171359  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataReaderExtension Microsoft.ReportingServices.DataExtensions.MappingDataReader::m_dataReaderExtension
0x17135e  ldarg.0
0x17135f  ldarg.1
0x171360  call     instance int32 Microsoft.ReportingServices.DataExtensions.MappingDataReader::GetFieldIndex(int32 aliasIndex)
0x171365  callvirt instance bool [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataReaderExtension::IsAggregationField(int32)
0x17136a  stloc.0
0x17136b  leave.s  loc_171389
0x17136d  stloc.1
0x17136e  ldc.i4   0xAE
0x171373  ldloc.1
0x171374  ldc.i4.1
0x171375  newarr   [mscorlib]System.Object
0x17137a  dup
0x17137b  ldc.i4.0
0x17137c  ldarg.0
0x17137d  ldfld    string Microsoft.ReportingServices.DataExtensions.MappingDataReader::m_dataSetName
0x171382  stelem.ref
0x171383  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportProcessingException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode code, class [mscorlib]System.Exception innerException, object[] arguments)
0x171388  throw
0x171389  ldloc.0
0x17138a  ret
```
