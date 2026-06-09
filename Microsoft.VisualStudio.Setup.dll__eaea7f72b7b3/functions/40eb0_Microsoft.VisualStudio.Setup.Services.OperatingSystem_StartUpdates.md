# Microsoft.VisualStudio.Setup.Services.OperatingSystem::StartUpdates

- ea: `0x40eb0`
- end: `0x40f84`
- name: `Microsoft.VisualStudio.Setup.Services.OperatingSystem::StartUpdates`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x40eb0`

## string_xrefs

- `0x40eec`: `The windows update service status is currently set to {0}`
- `0x40f20`: `Starting the windows update service.`
- `0x40f50`: `The windows update service status is now set to {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x40eb0  ldarg.0
0x40eb1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.OperatingSystem::logger
0x40eb6  dup
0x40eb7  brtrue.s loc_40ED6
0x40eb9  pop
0x40eba  ldarg.0
0x40ebb  ldarg.0
0x40ebc  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Services.OperatingSystem::services
0x40ec1  dup
0x40ec2  brtrue.s loc_40EC8
0x40ec4  pop
0x40ec5  ldnull
0x40ec6  br.s     loc_40ECE
0x40ec8  ldc.i4.0
0x40ec9  call     T0x2B000001
0x40ece  dup
0x40ecf  stloc.1
0x40ed0  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.OperatingSystem::logger
0x40ed5  ldloc.1
0x40ed6  stloc.0
0x40ed7  newobj   instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::.ctor()
0x40edc  dup
0x40edd  ldsfld   string Microsoft.VisualStudio.Setup.Services.OperatingSystem::WindowsUpdateService
0x40ee2  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::set_ServiceName(string)
0x40ee7  stloc.2
0x40ee8  ldloc.0
0x40ee9  brfalse.s loc_40F13
0x40eeb  ldloc.0
0x40eec  ldstr    aTheWindowsUpda// "The windows update service status is cu"...
0x40ef1  ldc.i4.1
0x40ef2  newarr   [mscorlib]System.Object
0x40ef7  dup
0x40ef8  ldc.i4.0
0x40ef9  ldloc.2
0x40efa  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x40eff  stloc.3
0x40f00  ldloca.s 3
0x40f02  constrained. [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus
0x40f08  callvirt instance string [mscorlib]System.Object::ToString()
0x40f0d  stelem.ref
0x40f0e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x40f13  ldloc.2
0x40f14  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x40f19  ldc.i4.4
0x40f1a  beq.s    loc_40F77
0x40f1c  ldloc.0
0x40f1d  brfalse.s loc_40F2F
0x40f1f  ldloc.0
0x40f20  ldstr    aStartingTheWin// "Starting the windows update service."
0x40f25  call     T0x2B000003
0x40f2a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x40f2f  ldloc.2
0x40f30  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Start()
0x40f35  ldloc.2
0x40f36  ldc.i4.4
0x40f37  ldc.r8   5.0
0x40f40  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x40f45  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0x40f4a  ldloc.0
0x40f4b  brtrue.s loc_40F4F
0x40f4d  leave.s  loc_40F83
0x40f4f  ldloc.0
0x40f50  ldstr    aTheWindowsUpda_0// "The windows update service status is no"...
0x40f55  ldc.i4.1
0x40f56  newarr   [mscorlib]System.Object
0x40f5b  dup
0x40f5c  ldc.i4.0
0x40f5d  ldloc.2
0x40f5e  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x40f63  stloc.3
0x40f64  ldloca.s 3
0x40f66  constrained. [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus
0x40f6c  callvirt instance string [mscorlib]System.Object::ToString()
0x40f71  stelem.ref
0x40f72  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x40f77  leave.s  loc_40F83
0x40f79  ldloc.2
0x40f7a  brfalse.s loc_40F82
0x40f7c  ldloc.2
0x40f7d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40f82  endfinally
0x40f83  ret
```
