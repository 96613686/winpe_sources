# <PollingMaintenanceLoop>d__23::MoveNext

- ea: `0x8f10`
- end: `0x90d0`
- name: `<PollingMaintenanceLoop>d__23::MoveNext`
- size: `448`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0xd10`
- `0xd20`
- `0xe30`
- `0x8ef0`
- `0x8f10`
- `0x90d0`

## string_xrefs

- `0x8ff2`: `PollingMaintenance: Polling cycle completed.`
- `0x906a`: `PollingMaintenance: Stopping Service because of severe error.`

## pseudocode

```c

```

## disassembly

```asm
0x8f10  ldarg.0
0x8f11  ldfld    int32 <PollingMaintenanceLoop>d__23::<>1__state
0x8f16  stloc.1
0x8f17  ldarg.0
0x8f18  ldfld    class Microsoft.ReportingServices.Library.DBPoll <PollingMaintenanceLoop>d__23::<>4__this
0x8f1d  stloc.2
0x8f1e  ldloc.1
0x8f1f  brfalse.s loc_8F2F
0x8f21  ldloc.1
0x8f22  ldc.i4.1
0x8f23  beq      loc_908E
0x8f28  ldc.i4.0
0x8f29  stloc.0
0x8f2a  leave    loc_90CE
0x8f2f  ldarg.0
0x8f30  ldc.i4.m1
0x8f31  stfld    int32 <PollingMaintenanceLoop>d__23::<>1__state
0x8f36  ldarg.0
0x8f37  ldnull
0x8f38  stfld    class [mscorlib]System.Exception <PollingMaintenanceLoop>d__23::<lastException>5__2
0x8f3d  ldloc.2
0x8f3e  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0x8f43  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x8f48  brfalse.s loc_8F5B
0x8f4a  ldloc.2
0x8f4b  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0x8f50  ldc.i4.3
0x8f51  ldstr    aPollingmainten// "PollingMaintenance: Polling started"
0x8f56  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x8f5b  ldarg.0
0x8f5c  ldc.i4.0
0x8f5d  stfld    int32 <PollingMaintenanceLoop>d__23::<timesToTrace>5__3
0x8f62  ldarg.0
0x8f63  ldc.i4.s 0xFD
0x8f65  stfld    int32 <PollingMaintenanceLoop>d__23::<>1__state
0x8f6a  nop
0x8f6b  ldsfld   class [mscorlib]System.Threading.AutoResetEvent Microsoft.ReportingServices.Library.DBPoll::m_resetEvent
0x8f70  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Reset()
0x8f75  pop
0x8f76  ldloc.2
0x8f77  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x8f7c  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.DBPoll::m_pollTimeStamp
0x8f81  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ResourceUtilities::get_TooMuchMemory()
0x8f86  brfalse.s loc_8FC3
0x8f88  ldarg.0
0x8f89  ldfld    int32 <PollingMaintenanceLoop>d__23::<timesToTrace>5__3
0x8f8e  brtrue.s loc_8FA0
0x8f90  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DbPollingTracer()
0x8f95  ldc.i4.3
0x8f96  ldstr    aPollingmainten_0// "PollingMaintenance: Skipping work item "...
0x8f9b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x8fa0  ldarg.0
0x8fa1  ldfld    int32 <PollingMaintenanceLoop>d__23::<timesToTrace>5__3
0x8fa6  stloc.3
0x8fa7  ldarg.0
0x8fa8  ldloc.3
0x8fa9  ldc.i4.1
0x8faa  add
0x8fab  stfld    int32 <PollingMaintenanceLoop>d__23::<timesToTrace>5__3
0x8fb0  ldarg.0
0x8fb1  ldfld    int32 <PollingMaintenanceLoop>d__23::<timesToTrace>5__3
0x8fb6  ldc.i4.s 0x1E
0x8fb8  ble.s    loc_901A
0x8fba  ldarg.0
0x8fbb  ldc.i4.0
0x8fbc  stfld    int32 <PollingMaintenanceLoop>d__23::<timesToTrace>5__3
0x8fc1  br.s     loc_901A
0x8fc3  ldloc.2
0x8fc4  ldarg.0
0x8fc5  ldflda   class [mscorlib]System.Exception <PollingMaintenanceLoop>d__23::<lastException>5__2
0x8fca  call     instance bool Microsoft.ReportingServices.Library.DBPoll::PollingFunction(class [mscorlib]System.Exception& lastException)
0x8fcf  brfalse.s loc_901A
0x8fd1  ldloc.2
0x8fd2  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0x8fd7  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_BufferOutput()
0x8fdc  brfalse.s loc_8FFC
0x8fde  ldloc.2
0x8fdf  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0x8fe4  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x8fe9  brfalse.s loc_8FFC
0x8feb  ldloc.2
0x8fec  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0x8ff1  ldc.i4.3
0x8ff2  ldstr    aPollingmainten_1// "PollingMaintenance: Polling cycle compl"...
0x8ff7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x8ffc  ldloc.2
0x8ffd  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0x9002  ldc.i4.0
0x9003  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::set_BufferOutput(bool)
0x9008  ldloc.2
0x9009  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0x900e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::WriteBuffer()
0x9013  ldarg.0
0x9014  ldnull
0x9015  stfld    class [mscorlib]System.Exception <PollingMaintenanceLoop>d__23::<lastException>5__2
0x901a  leave.s  loc_907C
0x901c  stloc.s  4
0x901e  ldloc.2
0x901f  ldstr    aPollingmainten_2// "PollingMaintenance"
0x9024  ldloc.s  4
0x9026  ldarg.0
0x9027  ldfld    class [mscorlib]System.Exception <PollingMaintenanceLoop>d__23::<lastException>5__2
0x902c  call     instance bool Microsoft.ReportingServices.Library.DBPoll::HandleException(string methodName, class [mscorlib]System.Exception e, class [mscorlib]System.Exception lastException)
0x9031  brtrue.s loc_903A
0x9033  ldc.i4.0
0x9034  stloc.0
0x9035  leave    loc_90BB
0x903a  ldarg.0
0x903b  ldloc.s  4
0x903d  stfld    class [mscorlib]System.Exception <PollingMaintenanceLoop>d__23::<lastException>5__2
0x9042  leave.s  loc_907C
0x9044  pop
0x9045  ldloc.2
0x9046  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0x904b  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x9050  brfalse.s loc_9074
0x9052  ldloc.2
0x9053  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0x9058  ldc.i4.1
0x9059  ldstr    aPollingmainten_3// "PollingMaintenance: Polling exiting fro"...
0x905e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x9063  ldloc.2
0x9064  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.DBPoll::m_tracer
0x9069  ldc.i4.1
0x906a  ldstr    aPollingmainten_4// "PollingMaintenance: Stopping Service be"...
0x906f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x9074  ldloc.2
0x9075  call     instance void Microsoft.ReportingServices.Library.DBPoll::ForceFullServiceStop()
0x907a  leave.s  loc_90B3
0x907c  ldarg.0
0x907d  ldnull
0x907e  stfld    object <PollingMaintenanceLoop>d__23::<>2__current
0x9083  ldarg.0
0x9084  ldc.i4.1
0x9085  stfld    int32 <PollingMaintenanceLoop>d__23::<>1__state
0x908a  ldc.i4.1
0x908b  stloc.0
0x908c  leave.s  loc_90CE
0x908e  ldarg.0
0x908f  ldc.i4.s 0xFD
0x9091  stfld    int32 <PollingMaintenanceLoop>d__23::<>1__state
0x9096  ldsfld   class [mscorlib]System.Threading.AutoResetEvent Microsoft.ReportingServices.Library.DBPoll::m_resetEvent
0x909b  ldloc.2
0x909c  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.DBPoll::m_pollInterval
0x90a1  ldc.i4.0
0x90a2  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(valuetype [mscorlib]System.TimeSpan, bool)
0x90a7  pop
0x90a8  ldloc.2
0x90a9  ldfld    bool Microsoft.ReportingServices.Library.DBPoll::m_continuePolling
0x90ae  brtrue   loc_8F6A
0x90b3  ldarg.0
0x90b4  call     instance void <PollingMaintenanceLoop>d__23::<>m__Finally1()
0x90b9  br.s     loc_90C3
0x90bb  ldarg.0
0x90bc  call     instance void <PollingMaintenanceLoop>d__23::<>m__Finally1()
0x90c1  leave.s  loc_90CE
0x90c3  ldc.i4.0
0x90c4  stloc.0
0x90c5  leave.s  loc_90CE
0x90c7  ldarg.0
0x90c8  call     instance void <PollingMaintenanceLoop>d__23::System.IDisposable.Dispose()
0x90cd  endfinally
0x90ce  ldloc.0
0x90cf  ret
```
