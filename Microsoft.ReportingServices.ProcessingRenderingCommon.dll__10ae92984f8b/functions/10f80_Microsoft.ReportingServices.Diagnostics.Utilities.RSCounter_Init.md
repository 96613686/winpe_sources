# Microsoft.ReportingServices.Diagnostics.Utilities.RSCounter::Init

- ea: `0x10f80`
- end: `0x11076`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.RSCounter::Init`
- size: `246`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x10f40`
- `0x10f60`

## callees

- `0x10f80`
- `0x123b0`
- `0x12480`

## string_xrefs

- `0x11004`: `Counter not created.  Category: {0}, Counter: {1}, Instance: {2}.  Error Message: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x10f80  ldnull
0x10f81  stloc.0
0x10f82  ldarg.0
0x10f83  ldarg.s  4
0x10f85  stfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.Utilities.RSCounter::m_Tracer
0x10f8a  ldarg.1
0x10f8b  brtrue.s loc_10F92
0x10f8d  leave    loc_11075
0x10f92  ldarg.3
0x10f93  ldstr    aUnittestsProce// "UnitTests.Processing"
0x10f98  call     bool [mscorlib]System.String::op_Equality(string, string)
0x10f9d  brfalse.s loc_10FA4
0x10f9f  leave    loc_11075
0x10fa4  ldarg.1
0x10fa5  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x10faa  brtrue.s loc_10FB1
0x10fac  leave    loc_11075
0x10fb1  ldarg.0
0x10fb2  ldarg.2
0x10fb3  stfld    string Microsoft.ReportingServices.Diagnostics.Utilities.RSCounter::m_name
0x10fb8  ldarg.0
0x10fb9  ldarg.1
0x10fba  ldarg.2
0x10fbb  ldarg.3
0x10fbc  ldc.i4.0
0x10fbd  newobj   instance void [System]System.Diagnostics.PerformanceCounter::.ctor(string, string, string, bool)
0x10fc2  stfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.ReportingServices.Diagnostics.Utilities.RSCounter::m_PerformanceCounter
0x10fc7  ldarg.s  5
0x10fc9  brfalse.s loc_10FD8
0x10fcb  ldarg.0
0x10fcc  ldfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.ReportingServices.Diagnostics.Utilities.RSCounter::m_PerformanceCounter
0x10fd1  ldc.i4.0
0x10fd2  conv.i8
0x10fd3  callvirt instance void [System]System.Diagnostics.PerformanceCounter::set_RawValue(int64)
0x10fd8  leave.s  loc_10FE0
0x10fda  stloc.0
0x10fdb  leave.s  loc_10FE0
0x10fdd  stloc.0
0x10fde  leave.s  loc_10FE0
0x10fe0  ldloc.0
0x10fe1  brfalse  loc_11075
0x10fe6  ldarg.0
0x10fe7  ldnull
0x10fe8  stfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.ReportingServices.Diagnostics.Utilities.RSCounter::m_PerformanceCounter
0x10fed  ldarg.0
0x10fee  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.Utilities.RSCounter::m_Tracer
0x10ff3  brfalse.s loc_11057
0x10ff5  ldarg.0
0x10ff6  ldfld    bool Microsoft.ReportingServices.Diagnostics.Utilities.RSCounter::m_isPrivateCounter
0x10ffb  brfalse.s loc_1102B
0x10ffd  ldarg.0
0x10ffe  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.Utilities.RSCounter::m_Tracer
0x11003  ldc.i4.4
0x11004  ldstr    aCounterNotCrea// "Counter not created.  Category: {0}, Co"...
0x11009  ldc.i4.4
0x1100a  newarr   [mscorlib]System.Object
0x1100f  dup
0x11010  ldc.i4.0
0x11011  ldarg.1
0x11012  stelem.ref
0x11013  dup
0x11014  ldc.i4.1
0x11015  ldarg.2
0x11016  stelem.ref
0x11017  dup
0x11018  ldc.i4.2
0x11019  ldarg.3
0x1101a  stelem.ref
0x1101b  dup
0x1101c  ldc.i4.3
0x1101d  ldloc.0
0x1101e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x11023  stelem.ref
0x11024  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x11029  br.s     loc_11057
0x1102b  ldarg.0
0x1102c  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.Utilities.RSCounter::m_Tracer
0x11031  ldc.i4.1
0x11032  ldstr    aErrorCreatingC// "Error creating counter.  Category: {0},"...
0x11037  ldc.i4.4
0x11038  newarr   [mscorlib]System.Object
0x1103d  dup
0x1103e  ldc.i4.0
0x1103f  ldarg.1
0x11040  stelem.ref
0x11041  dup
0x11042  ldc.i4.1
0x11043  ldarg.2
0x11044  stelem.ref
0x11045  dup
0x11046  ldc.i4.2
0x11047  ldarg.3
0x11048  stelem.ref
0x11049  dup
0x1104a  ldc.i4.3
0x1104b  ldloc.0
0x1104c  callvirt instance string [mscorlib]System.Object::ToString()
0x11051  stelem.ref
0x11052  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x11057  ldarg.0
0x11058  ldfld    bool Microsoft.ReportingServices.Diagnostics.Utilities.RSCounter::m_isPrivateCounter
0x1105d  brtrue.s loc_11075
0x1105f  call     class Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x11064  ldc.i4.s 0x71
0x11066  ldc.i4.1
0x11067  newarr   [mscorlib]System.Object
0x1106c  dup
0x1106d  ldc.i4.0
0x1106e  ldarg.2
0x1106f  stelem.ref
0x11070  callvirt instance void Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteError(valuetype Microsoft.ReportingServices.Diagnostics.Event id, object[] args)
0x11075  ret
```
