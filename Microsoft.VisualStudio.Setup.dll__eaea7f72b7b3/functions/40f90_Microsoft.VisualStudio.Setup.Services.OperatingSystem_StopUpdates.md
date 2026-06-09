# Microsoft.VisualStudio.Setup.Services.OperatingSystem::StopUpdates

- ea: `0x40f90`
- end: `0x41095`
- name: `Microsoft.VisualStudio.Setup.Services.OperatingSystem::StopUpdates`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x40f90`

## string_xrefs

- `0x40fcc`: `The windows update service status is currently set to {0}`
- `0x41041`: `The windows update service status is now set to {0}.`
- `0x41011`: `Stopping the windows update service.`

## pseudocode

```c

```

## disassembly

```asm
0x40f90  ldarg.0
0x40f91  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.OperatingSystem::logger
0x40f96  dup
0x40f97  brtrue.s loc_40FB6
0x40f99  pop
0x40f9a  ldarg.0
0x40f9b  ldarg.0
0x40f9c  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Services.OperatingSystem::services
0x40fa1  dup
0x40fa2  brtrue.s loc_40FA8
0x40fa4  pop
0x40fa5  ldnull
0x40fa6  br.s     loc_40FAE
0x40fa8  ldc.i4.0
0x40fa9  call     T0x2B000001
0x40fae  dup
0x40faf  stloc.1
0x40fb0  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.OperatingSystem::logger
0x40fb5  ldloc.1
0x40fb6  stloc.0
0x40fb7  newobj   instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::.ctor()
0x40fbc  dup
0x40fbd  ldsfld   string Microsoft.VisualStudio.Setup.Services.OperatingSystem::WindowsUpdateService
0x40fc2  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::set_ServiceName(string)
0x40fc7  stloc.2
0x40fc8  ldloc.0
0x40fc9  brfalse.s loc_40FF3
0x40fcb  ldloc.0
0x40fcc  ldstr    aTheWindowsUpda// "The windows update service status is cu"...
0x40fd1  ldc.i4.1
0x40fd2  newarr   [mscorlib]System.Object
0x40fd7  dup
0x40fd8  ldc.i4.0
0x40fd9  ldloc.2
0x40fda  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x40fdf  stloc.3
0x40fe0  ldloca.s 3
0x40fe2  constrained. [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus
0x40fe8  callvirt instance string [mscorlib]System.Object::ToString()
0x40fed  stelem.ref
0x40fee  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x40ff3  ldloc.2
0x40ff4  callvirt instance bool [System.ServiceProcess]System.ServiceProcess.ServiceController::get_CanStop()
0x40ff9  brfalse.s loc_4106A
0x40ffb  ldloc.2
0x40ffc  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x41001  ldc.i4.1
0x41002  beq.s    loc_4106A
0x41004  ldloc.2
0x41005  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x4100a  ldc.i4.3
0x4100b  beq.s    loc_4106A
0x4100d  ldloc.0
0x4100e  brfalse.s loc_41020
0x41010  ldloc.0
0x41011  ldstr    aStoppingTheWin// "Stopping the windows update service."
0x41016  call     T0x2B000003
0x4101b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x41020  ldloc.2
0x41021  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Stop()
0x41026  ldloc.2
0x41027  ldc.i4.1
0x41028  ldc.r8   5.0
0x41031  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x41036  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0x4103b  ldloc.0
0x4103c  brtrue.s loc_41040
0x4103e  leave.s  loc_41094
0x41040  ldloc.0
0x41041  ldstr    aTheWindowsUpda_0// "The windows update service status is no"...
0x41046  ldc.i4.1
0x41047  newarr   [mscorlib]System.Object
0x4104c  dup
0x4104d  ldc.i4.0
0x4104e  ldloc.2
0x4104f  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x41054  stloc.3
0x41055  ldloca.s 3
0x41057  constrained. [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus
0x4105d  callvirt instance string [mscorlib]System.Object::ToString()
0x41062  stelem.ref
0x41063  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x41068  leave.s  loc_41094
0x4106a  ldloc.2
0x4106b  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x41070  ldc.i4.3
0x41071  bne.un.s loc_41088
0x41073  ldloc.2
0x41074  ldc.i4.1
0x41075  ldc.r8   5.0
0x4107e  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x41083  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0x41088  leave.s  loc_41094
0x4108a  ldloc.2
0x4108b  brfalse.s loc_41093
0x4108d  ldloc.2
0x4108e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41093  endfinally
0x41094  ret
```
