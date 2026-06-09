# Microsoft.BIServer.Configuration.RsService::AskReportServerToShutDown

- ea: `0x3390`
- end: `0x3493`
- name: `Microsoft.BIServer.Configuration.RsService::AskReportServerToShutDown`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3360`

## callees

- `0x3390`
- `0x34a0`

## string_xrefs

- `0x33e4`: `Process '{0}' still running after service stopped. Waiting...`

## pseudocode

```c

```

## disassembly

```asm
0x3390  ldarg.0
0x3391  ldfld    string Microsoft.BIServer.Configuration.RsService::_serviceName
0x3396  newobj   instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::.ctor(string)
0x339b  stloc.0
0x339c  ldloc.0
0x339d  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x33a2  ldc.i4.2
0x33a3  bne.un.s loc_33AD
0x33a5  ldloc.0
0x33a6  ldc.i4.4
0x33a7  ldarg.1
0x33a8  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0x33ad  ldarg.0
0x33ae  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System]System.Diagnostics.Process> Microsoft.BIServer.Configuration.RsService::GetProcesses()
0x33b3  call     T0x2B00002C
0x33b8  ldloc.0
0x33b9  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x33be  ldc.i4.4
0x33bf  bne.un.s loc_33C7
0x33c1  ldloc.0
0x33c2  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Stop()
0x33c7  ldloc.0
0x33c8  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x33cd  ldc.i4.1
0x33ce  beq.s    loc_33D8
0x33d0  ldloc.0
0x33d1  ldc.i4.1
0x33d2  ldarg.1
0x33d3  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0x33d8  stloc.1
0x33d9  ldc.i4.0
0x33da  stloc.2
0x33db  br       loc_3463
0x33e0  ldloc.1
0x33e1  ldloc.2
0x33e2  ldelem.ref
0x33e3  stloc.3
0x33e4  ldstr    aProcess0StillR// "Process '{0}' still running after servi"...
0x33e9  ldc.i4.1
0x33ea  newarr   [mscorlib]System.Object
0x33ef  dup
0x33f0  ldc.i4.0
0x33f1  ldloc.3
0x33f2  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x33f7  box      [mscorlib]System.Int32
0x33fc  stelem.ref
0x33fd  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Debug(string, object[])
0x3402  ldloc.3
0x3403  ldarga.s 1
0x3405  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x340a  conv.i4
0x340b  callvirt instance bool [System]System.Diagnostics.Process::WaitForExit(int32)
0x3410  pop
0x3411  ldloc.3
0x3412  callvirt instance bool [System]System.Diagnostics.Process::get_HasExited()
0x3417  brtrue.s loc_345F
0x3419  ldstr    aProcess0StillR_0// "Process '{0}' still running after wait."...
0x341e  ldc.i4.1
0x341f  newarr   [mscorlib]System.Object
0x3424  dup
0x3425  ldc.i4.0
0x3426  ldloc.3
0x3427  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x342c  box      [mscorlib]System.Int32
0x3431  stelem.ref
0x3432  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Debug(string, object[])
0x3437  ldloc.3
0x3438  callvirt instance void [System]System.Diagnostics.Process::Kill()
0x343d  leave.s  loc_345F
0x343f  ldstr    aFailedToKillPr// "Failed to kill process '{0}'."
0x3444  ldc.i4.1
0x3445  newarr   [mscorlib]System.Object
0x344a  dup
0x344b  ldc.i4.0
0x344c  ldloc.3
0x344d  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x3452  box      [mscorlib]System.Int32
0x3457  stelem.ref
0x3458  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Debug(class [mscorlib]System.Exception, string, object[])
0x345d  leave.s  loc_345F
0x345f  ldloc.2
0x3460  ldc.i4.1
0x3461  add
0x3462  stloc.2
0x3463  ldloc.2
0x3464  ldloc.1
0x3465  ldlen
0x3466  conv.i4
0x3467  blt      loc_33E0
0x346c  leave.s  loc_3478
0x346e  ldloc.0
0x346f  brfalse.s loc_3477
0x3471  ldloc.0
0x3472  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3477  endfinally
0x3478  leave.s  loc_348E
0x347a  ldstr    aExceptionEncou// "Exception encountered shutting down rep"...
0x347f  call     T0x2B000015
0x3484  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Fatal(class [mscorlib]System.Exception, string, object[])
0x3489  ldc.i4.0
0x348a  stloc.s  4
0x348c  leave.s  loc_3490
0x348e  ldc.i4.1
0x348f  ret
0x3490  ldloc.s  4
0x3492  ret
```
