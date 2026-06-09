# Microsoft.ReportingServices.Diagnostics.ApplicationParameter::InvalidInputSetDefault

- ea: `0x1480`
- end: `0x14f2`
- name: `Microsoft.ReportingServices.Diagnostics.ApplicationParameter::InvalidInputSetDefault`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1350`

## callees

- `0x1480`
- `0x1500`

## pseudocode

```c

```

## disassembly

```asm
0x1480  ldarg.0
0x1481  ldarg.0
0x1482  ldfld    object Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_BaseDefaultValue
0x1487  stfld    object Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_BaseValue
0x148c  ldarg.0
0x148d  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_Tracer
0x1492  brfalse.s loc_14F1
0x1494  ldarg.0
0x1495  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_Tracer
0x149a  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x149f  brfalse.s loc_14F1
0x14a1  ldarg.0
0x14a2  call     instance void Microsoft.ReportingServices.Diagnostics.ApplicationParameter::WriteInvalidConfigEntry()
0x14a7  ldarg.0
0x14a8  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_Tracer
0x14ad  ldc.i4.2
0x14ae  ldarg.0
0x14af  ldfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_TraceWrong
0x14b4  ldc.i4.5
0x14b5  newarr   [mscorlib]System.Object
0x14ba  dup
0x14bb  ldc.i4.0
0x14bc  ldarg.0
0x14bd  ldfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_name
0x14c2  stelem.ref
0x14c3  dup
0x14c4  ldc.i4.1
0x14c5  ldarg.0
0x14c6  ldfld    object Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_BaseValue
0x14cb  stelem.ref
0x14cc  dup
0x14cd  ldc.i4.2
0x14ce  ldarg.0
0x14cf  ldfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_Units
0x14d4  stelem.ref
0x14d5  dup
0x14d6  ldc.i4.3
0x14d7  ldarg.0
0x14d8  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_ParameterSource
0x14dd  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource::GetSourceNameForTrace()
0x14e2  stelem.ref
0x14e3  dup
0x14e4  ldc.i4.4
0x14e5  ldarg.0
0x14e6  ldfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_configValue
0x14eb  stelem.ref
0x14ec  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x14f1  ret
```
