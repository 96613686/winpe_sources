# Microsoft.ReportingServices.Diagnostics.ApplicationParameter::InterpretValue

- ea: `0x1350`
- end: `0x1472`
- name: `Microsoft.ReportingServices.Diagnostics.ApplicationParameter::InterpretValue`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1240`

## callees

- `0x1200`
- `0x1340`
- `0x1350`
- `0x1480`

## pseudocode

```c

```

## disassembly

```asm
0x1350  ldarg.0
0x1351  ldfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_configValue
0x1356  brtrue.s loc_13CC
0x1358  ldarg.0
0x1359  ldarg.0
0x135a  ldfld    object Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_BaseDefaultValue
0x135f  stfld    object Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_BaseValue
0x1364  ldarg.0
0x1365  ldfld    bool Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_traceUsingDefault
0x136a  brfalse  loc_1471
0x136f  ldarg.0
0x1370  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_Tracer
0x1375  brfalse  loc_1471
0x137a  ldarg.0
0x137b  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_Tracer
0x1380  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x1385  brfalse  loc_1471
0x138a  ldarg.0
0x138b  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_Tracer
0x1390  ldc.i4.3
0x1391  ldarg.0
0x1392  ldfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_TraceAbsent
0x1397  ldc.i4.4
0x1398  newarr   [mscorlib]System.Object
0x139d  dup
0x139e  ldc.i4.0
0x139f  ldarg.0
0x13a0  ldfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_name
0x13a5  stelem.ref
0x13a6  dup
0x13a7  ldc.i4.1
0x13a8  ldarg.0
0x13a9  ldfld    object Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_BaseValue
0x13ae  stelem.ref
0x13af  dup
0x13b0  ldc.i4.2
0x13b1  ldarg.0
0x13b2  ldfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_Units
0x13b7  stelem.ref
0x13b8  dup
0x13b9  ldc.i4.3
0x13ba  ldarg.0
0x13bb  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_ParameterSource
0x13c0  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource::GetSourceNameForTrace()
0x13c5  stelem.ref
0x13c6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x13cb  ret
0x13cc  nop
0x13cd  ldarg.0
0x13ce  ldarg.0
0x13cf  ldfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_configValue
0x13d4  ldloca.s 0
0x13d6  callvirt instance bool Microsoft.ReportingServices.Diagnostics.ApplicationParameter::Validate(string valueToValidate, [out] object& validatedValue)
0x13db  brfalse.s loc_1444
0x13dd  ldarg.0
0x13de  ldloc.0
0x13df  stfld    object Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_BaseValue
0x13e4  ldarg.0
0x13e5  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_Tracer
0x13ea  brfalse.s loc_144A
0x13ec  ldarg.0
0x13ed  call     instance bool Microsoft.ReportingServices.Diagnostics.ApplicationParameter::get_TraceSuccess()
0x13f2  brfalse.s loc_144A
0x13f4  ldarg.0
0x13f5  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_Tracer
0x13fa  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x13ff  brfalse.s loc_144A
0x1401  ldarg.0
0x1402  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_Tracer
0x1407  ldc.i4.3
0x1408  ldarg.0
0x1409  ldfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_TraceRead
0x140e  ldc.i4.4
0x140f  newarr   [mscorlib]System.Object
0x1414  dup
0x1415  ldc.i4.0
0x1416  ldarg.0
0x1417  ldfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_name
0x141c  stelem.ref
0x141d  dup
0x141e  ldc.i4.1
0x141f  ldarg.0
0x1420  ldfld    object Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_BaseValue
0x1425  stelem.ref
0x1426  dup
0x1427  ldc.i4.2
0x1428  ldarg.0
0x1429  ldfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_Units
0x142e  stelem.ref
0x142f  dup
0x1430  ldc.i4.3
0x1431  ldarg.0
0x1432  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_ParameterSource
0x1437  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource::GetSourceNameForTrace()
0x143c  stelem.ref
0x143d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1442  br.s     loc_144A
0x1444  ldarg.0
0x1445  call     instance void Microsoft.ReportingServices.Diagnostics.ApplicationParameter::InvalidInputSetDefault()
0x144a  leave.s  loc_1471
0x144c  stloc.1
0x144d  ldloc.1
0x144e  isinst   [mscorlib]System.ArgumentException
0x1453  brtrue.s loc_1465
0x1455  ldloc.1
0x1456  isinst   [mscorlib]System.FormatException
0x145b  brtrue.s loc_1465
0x145d  ldloc.1
0x145e  isinst   [mscorlib]System.OverflowException
0x1463  brfalse.s loc_146D
0x1465  ldarg.0
0x1466  call     instance void Microsoft.ReportingServices.Diagnostics.ApplicationParameter::InvalidInputSetDefault()
0x146b  br.s     loc_146F
0x146d  rethrow
0x146f  leave.s  loc_1471
0x1471  ret
```
