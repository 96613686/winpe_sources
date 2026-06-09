# Microsoft.ReportingServices.Library.ProcessorUtilities::get_ProcessCPUPercentage

- ea: `0x7ab0`
- end: `0x7b1d`
- name: `Microsoft.ReportingServices.Library.ProcessorUtilities::get_ProcessCPUPercentage`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x19b0`
- `0x1c80`

## callees

- `0x7a50`
- `0x7ab0`

## pseudocode

```c

```

## disassembly

```asm
0x7ab0  ldc.r8   0.0
0x7ab9  stloc.0
0x7aba  ldloca.s 1
0x7abc  call     int64 [ReportingServicesNativeClient]Microsoft.ReportingServices.Utilities.ProcessUtilities::GetProcessTimes()
0x7ac1  call     instance void [mscorlib]System.TimeSpan::.ctor(int64)
0x7ac6  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x7acb  stloc.2
0x7acc  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.ProcessorUtilities::m_lastReadTime
0x7ad1  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Zero
0x7ad6  call     bool [mscorlib]System.TimeSpan::op_Inequality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x7adb  brfalse.s loc_7B0F
0x7add  ldloc.2
0x7ade  ldsfld   valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.ProcessorUtilities::m_lastReadDate
0x7ae3  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x7ae8  stloc.3
0x7ae9  ldloca.s 1
0x7aeb  call     instance int64 [mscorlib]System.TimeSpan::get_Ticks()
0x7af0  ldsflda  valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.ProcessorUtilities::m_lastReadTime
0x7af5  call     instance int64 [mscorlib]System.TimeSpan::get_Ticks()
0x7afa  sub
0x7afb  conv.r8
0x7afc  ldloca.s 3
0x7afe  call     instance int64 [mscorlib]System.TimeSpan::get_Ticks()
0x7b03  conv.r8
0x7b04  div
0x7b05  stloc.0
0x7b06  ldloc.0
0x7b07  call     int32 Microsoft.ReportingServices.Library.ProcessorUtilities::get_ProcessorsInUse()
0x7b0c  conv.r8
0x7b0d  div
0x7b0e  stloc.0
0x7b0f  ldloc.2
0x7b10  stsfld   valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.ProcessorUtilities::m_lastReadDate
0x7b15  ldloc.1
0x7b16  stsfld   valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.ProcessorUtilities::m_lastReadTime
0x7b1b  ldloc.0
0x7b1c  ret
```
