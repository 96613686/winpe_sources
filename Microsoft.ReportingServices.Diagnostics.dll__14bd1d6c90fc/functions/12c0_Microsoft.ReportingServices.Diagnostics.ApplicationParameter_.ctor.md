# Microsoft.ReportingServices.Diagnostics.ApplicationParameter::.ctor

- ea: `0x12c0`
- end: `0x1339`
- name: `Microsoft.ReportingServices.Diagnostics.ApplicationParameter::.ctor`
- size: `121`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1530`
- `0x1590`
- `0x1840`
- `0x1910`
- `0x2800`
- `0x9390`
- `0x93e0`

## pseudocode

```c

```

## disassembly

```asm
0x12c0  ldarg.0
0x12c1  ldc.i4.1
0x12c2  stfld    bool Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_traceSuccess
0x12c7  ldarg.0
0x12c8  ldc.i4.1
0x12c9  stfld    bool Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_traceUsingDefault
0x12ce  ldarg.0
0x12cf  ldstr    asc_126C2// ""
0x12d4  stfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_Units
0x12d9  ldarg.0
0x12da  ldstr    asc_126C2// ""
0x12df  stfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_name
0x12e4  ldarg.0
0x12e5  ldstr    aInitializing0T// "Initializing {0} to '{1}' {2} as specif"...
0x12ea  stfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_TraceRead
0x12ef  ldarg.0
0x12f0  ldstr    aInitializing0T_0// "Initializing {0} to default value of '{"...
0x12f5  stfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_TraceAbsent
0x12fa  ldarg.0
0x12fb  ldstr    aInitializing0T_1// "Initializing {0} to default value of '{"...
0x1300  stfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_TraceWrong
0x1305  ldarg.0
0x1306  call     instance void [mscorlib]System.Object::.ctor()
0x130b  ldarg.0
0x130c  ldarg.1
0x130d  stfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_ParameterSource
0x1312  ldarg.0
0x1313  ldarg.2
0x1314  stfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_Tracer
0x1319  ldarg.0
0x131a  ldarg.3
0x131b  stfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_name
0x1320  ldarg.0
0x1321  ldarg.s  4
0x1323  stfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_configValue
0x1328  ldarg.0
0x1329  ldarg.s  5
0x132b  stfld    object Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_BaseDefaultValue
0x1330  ldarg.0
0x1331  ldarg.s  6
0x1333  stfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_Units
0x1338  ret
```
