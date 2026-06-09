# Microsoft.ReportingServices.Library.CachedSystemProperties::get_ExecutionLogLevel

- ea: `0x460`
- end: `0x4ab`
- name: `Microsoft.ReportingServices.Library.CachedSystemProperties::get_ExecutionLogLevel`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x130`
- `0x460`

## pseudocode

```c

```

## disassembly

```asm
0x460  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.EnumParameter`1<valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExecutionLogLevel> Microsoft.ReportingServices.Library.CachedSystemProperties::m_executionLogLevelParam
0x465  brtrue.s loc_4A0
0x467  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x46c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x471  ldstr    aExecutionlogle// "ExecutionLogLevel"
0x476  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x47b  ldstr    aExecutionlogle// "ExecutionLogLevel"
0x480  callvirt instance string Microsoft.ReportingServices.Library.CachedSystemProperties::GetParameter(string name)
0x485  ldc.i4.0
0x486  ldsfld   string [mscorlib]System.String::Empty
0x48b  newobj   instance void class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.EnumParameter`1<valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExecutionLogLevel>::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace, string, string, var<u1>, !!T0)
0x490  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.EnumParameter`1<valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExecutionLogLevel> Microsoft.ReportingServices.Library.CachedSystemProperties::m_executionLogLevelParam
0x495  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.EnumParameter`1<valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExecutionLogLevel> Microsoft.ReportingServices.Library.CachedSystemProperties::m_executionLogLevelParam
0x49a  ldc.i4.1
0x49b  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ApplicationParameter::set_TraceSuccess(bool)
0x4a0  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.EnumParameter`1<valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExecutionLogLevel> Microsoft.ReportingServices.Library.CachedSystemProperties::m_executionLogLevelParam
0x4a5  callvirt instance var<u1> class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.EnumParameter`1<valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExecutionLogLevel>::get_Value()
0x4aa  ret
```
