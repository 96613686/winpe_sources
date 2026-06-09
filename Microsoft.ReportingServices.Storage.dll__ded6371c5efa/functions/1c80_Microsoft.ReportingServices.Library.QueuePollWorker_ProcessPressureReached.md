# Microsoft.ReportingServices.Library.QueuePollWorker::ProcessPressureReached

- ea: `0x1c80`
- end: `0x1d50`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::ProcessPressureReached`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a50`

## callees

- `0x1c80`
- `0x7ab0`

## string_xrefs

- `0x1cc2`: `Paused polling, thread pressure reached: `

## pseudocode

```c

```

## disassembly

```asm
0x1c80  ldc.i4.0
0x1c81  stloc.0
0x1c82  ldc.i4.0
0x1c83  stloc.1
0x1c84  ldc.i4.0
0x1c85  stloc.2
0x1c86  ldc.i4.0
0x1c87  stloc.3
0x1c88  ldloca.s 0
0x1c8a  ldloca.s 1
0x1c8c  call     void [mscorlib]System.Threading.ThreadPool::GetAvailableThreads(int32&, int32&)
0x1c91  ldloca.s 2
0x1c93  ldloca.s 3
0x1c95  call     void [mscorlib]System.Threading.ThreadPool::GetMaxThreads(int32&, int32&)
0x1c9a  ldloc.2
0x1c9b  ldloc.0
0x1c9c  sub
0x1c9d  stloc.s  4
0x1c9f  ldloc.s  4
0x1ca1  conv.r8
0x1ca2  ldloc.2
0x1ca3  conv.r8
0x1ca4  ldc.r8   0.75
0x1cad  mul
0x1cae  ble.un.s loc_1CDF
0x1cb0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DbPollingTracer()
0x1cb5  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x1cba  brfalse.s loc_1CDD
0x1cbc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DbPollingTracer()
0x1cc1  ldc.i4.4
0x1cc2  ldstr    aPausedPollingT// "Paused polling, thread pressure reached"...
0x1cc7  ldloca.s 4
0x1cc9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1cce  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1cd3  call     string [mscorlib]System.String::Concat(string, string)
0x1cd8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1cdd  ldc.i4.1
0x1cde  ret
0x1cdf  call     float64 Microsoft.ReportingServices.Library.ProcessorUtilities::get_ProcessCPUPercentage()
0x1ce4  stloc.s  5
0x1ce6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DbPollingTracer()
0x1ceb  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x1cf0  brfalse.s loc_1D12
0x1cf2  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DbPollingTracer()
0x1cf7  ldc.i4.4
0x1cf8  ldstr    aCpuPercentage0// "CPU percentage = {0}"
0x1cfd  ldc.i4.1
0x1cfe  newarr   [mscorlib]System.Object
0x1d03  dup
0x1d04  ldc.i4.0
0x1d05  ldloc.s  5
0x1d07  box      [mscorlib]System.Double
0x1d0c  stelem.ref
0x1d0d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1d12  ldloc.s  5
0x1d14  ldc.r8   0.5
0x1d1d  ble.un.s loc_1D4E
0x1d1f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DbPollingTracer()
0x1d24  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x1d29  brfalse.s loc_1D4C
0x1d2b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DbPollingTracer()
0x1d30  ldc.i4.4
0x1d31  ldstr    aPausedPollingC// "Paused polling, CPU pressure reached: "
0x1d36  ldloca.s 5
0x1d38  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d3d  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0x1d42  call     string [mscorlib]System.String::Concat(string, string)
0x1d47  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1d4c  ldc.i4.1
0x1d4d  ret
0x1d4e  ldc.i4.0
0x1d4f  ret
```
