# Microsoft.BIServer.BIService.ManagedProcess::Start

- ea: `0x1f10`
- end: `0x1f92`
- name: `Microsoft.BIServer.BIService.ManagedProcess::Start`
- size: `130`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800`
- `0x1850`
- `0x35f0`
- `0x3a90`

## callees

- `0x1bd0`
- `0x1f10`
- `0x1fa0`
- `0x20d0`
- `0x2c70`

## string_xrefs

- `0x1f18`: `Attempting to Start a running process... ignoring request: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1f10  ldarg.0
0x1f11  call     instance bool Microsoft.BIServer.BIService.ManagedProcess::IsRunning()
0x1f16  brfalse.s loc_1F38
0x1f18  ldstr    aAttemptingToSt// "Attempting to Start a running process.."...
0x1f1d  ldc.i4.1
0x1f1e  newarr   [mscorlib]System.Object
0x1f23  dup
0x1f24  ldc.i4.0
0x1f25  ldarg.0
0x1f26  call     instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::get_ProcessConfig()
0x1f2b  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Name()
0x1f30  stelem.ref
0x1f31  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Warning(string, object[])
0x1f36  leave.s  loc_1F91
0x1f38  ldarg.0
0x1f39  ldarg.0
0x1f3a  ldfld    class Microsoft.BIServer.BIService.ProcessLaunchers.IProcessLauncher Microsoft.BIServer.BIService.ManagedProcess::_processLauncher
0x1f3f  callvirt instance class [System]System.Diagnostics.Process Microsoft.BIServer.BIService.ProcessLaunchers.IProcessLauncher::Start()
0x1f44  stfld    class [System]System.Diagnostics.Process Microsoft.BIServer.BIService.ManagedProcess::_process
0x1f49  ldarg.0
0x1f4a  ldfld    class [System]System.Diagnostics.Process Microsoft.BIServer.BIService.ManagedProcess::_process
0x1f4f  brfalse.s loc_1F68
0x1f51  ldarg.0
0x1f52  ldfld    class [System]System.Diagnostics.Process Microsoft.BIServer.BIService.ManagedProcess::_process
0x1f57  ldarg.0
0x1f58  ldftn    instance void Microsoft.BIServer.BIService.ManagedProcess::ProcessExitedHandler(object sender, class [mscorlib]System.EventArgs e)
0x1f5e  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1f63  callvirt instance void [System]System.Diagnostics.Process::add_Exited(class [mscorlib]System.EventHandler)
0x1f68  leave.s  loc_1F91
0x1f6a  stloc.0
0x1f6b  ldstr    aProcessFailedT// "Process failed to start: {0} due to exc"...
0x1f70  ldc.i4.2
0x1f71  newarr   [mscorlib]System.Object
0x1f76  dup
0x1f77  ldc.i4.0
0x1f78  ldarg.0
0x1f79  callvirt instance string [mscorlib]System.Object::ToString()
0x1f7e  stelem.ref
0x1f7f  dup
0x1f80  ldc.i4.1
0x1f81  ldloc.0
0x1f82  stelem.ref
0x1f83  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0x1f88  ldarg.0
0x1f89  ldnull
0x1f8a  stfld    class [System]System.Diagnostics.Process Microsoft.BIServer.BIService.ManagedProcess::_process
0x1f8f  leave.s  loc_1F91
0x1f91  ret
```
