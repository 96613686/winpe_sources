# Microsoft.ReportingServices.Library.CachedSystemProperties::get_EnableRemoteErrors

- ea: `0x3b0`
- end: `0x405`
- name: `Microsoft.ReportingServices.Library.CachedSystemProperties::get_EnableRemoteErrors`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140`
- `0x3b0`

## pseudocode

```c

```

## disassembly

```asm
0x3b0  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_EnableRemoteErrorsParam
0x3b5  brtrue.s loc_3F1
0x3b7  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x3bc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x3c1  ldstr    aEnableremoteer// "EnableRemoteErrors"
0x3c6  ldsfld   class Microsoft.ReportingServices.Library.CachedSystemProperties Microsoft.ReportingServices.Library.CachedSystemProperties::Instance
0x3cb  ldstr    aEnableremoteer// "EnableRemoteErrors"
0x3d0  ldc.i4.1
0x3d1  callvirt instance string Microsoft.ReportingServices.Library.CachedSystemProperties::GetParameter(string name, bool noThrow)
0x3d6  ldc.i4.0
0x3d7  ldstr    asc_A0B2// ""
0x3dc  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace, string, string, bool, string)
0x3e1  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_EnableRemoteErrorsParam
0x3e6  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_EnableRemoteErrorsParam
0x3eb  ldc.i4.1
0x3ec  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ApplicationParameter::set_TraceSuccess(bool)
0x3f1  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter Microsoft.ReportingServices.Library.CachedSystemProperties::m_EnableRemoteErrorsParam
0x3f6  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.BooleanParameter::get_Value()
0x3fb  stloc.0
0x3fc  leave.s  loc_403
0x3fe  pop
0x3ff  ldc.i4.0
0x400  stloc.0
0x401  leave.s  loc_403
0x403  ldloc.0
0x404  ret
```
