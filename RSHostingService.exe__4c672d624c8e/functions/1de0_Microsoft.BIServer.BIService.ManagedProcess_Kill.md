# Microsoft.BIServer.BIService.ManagedProcess::Kill

- ea: `0x1de0`
- end: `0x1ed8`
- name: `Microsoft.BIServer.BIService.ManagedProcess::Kill`
- size: `248`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d90`
- `0x1da0`

## callees

- `0x1bd0`
- `0x1de0`
- `0x1fa0`
- `0x20d0`

## string_xrefs

- `0x1e93`: `Process has already exited: {0}`
- `0x1eb9`: `Attempting to kill an unstarted process: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1de0  ldarg.0
0x1de1  ldfld    class [System]System.Diagnostics.Process Microsoft.BIServer.BIService.ManagedProcess::_process
0x1de6  brfalse  loc_1EB9
0x1deb  ldarg.0
0x1dec  call     instance bool Microsoft.BIServer.BIService.ManagedProcess::IsRunning()
0x1df1  brfalse  loc_1E93
0x1df6  ldstr    aKillingProcess// "Killing Process: {0}"
0x1dfb  ldc.i4.1
0x1dfc  newarr   [mscorlib]System.Object
0x1e01  dup
0x1e02  ldc.i4.0
0x1e03  ldarg.0
0x1e04  call     instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::get_ProcessConfig()
0x1e09  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Name()
0x1e0e  stelem.ref
0x1e0f  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x1e14  ldarg.0
0x1e15  ldfld    class [System]System.Diagnostics.Process Microsoft.BIServer.BIService.ManagedProcess::_process
0x1e1a  callvirt instance void [System]System.Diagnostics.Process::Kill()
0x1e1f  leave    loc_1EB1
0x1e24  stloc.0
0x1e25  ldstr    aCouldNotKillRu// "Could not kill running process: {0}, ex"...
0x1e2a  ldc.i4.2
0x1e2b  newarr   [mscorlib]System.Object
0x1e30  dup
0x1e31  ldc.i4.0
0x1e32  ldarg.0
0x1e33  ldfld    class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::_processConfig
0x1e38  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Name()
0x1e3d  stelem.ref
0x1e3e  dup
0x1e3f  ldc.i4.1
0x1e40  ldloc.0
0x1e41  stelem.ref
0x1e42  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0x1e47  leave.s  loc_1EB1
0x1e49  stloc.1
0x1e4a  ldstr    aCouldNotKillRe// "Could not kill REMOTE process: {0}, exc"...
0x1e4f  ldc.i4.2
0x1e50  newarr   [mscorlib]System.Object
0x1e55  dup
0x1e56  ldc.i4.0
0x1e57  ldarg.0
0x1e58  ldfld    class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::_processConfig
0x1e5d  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Name()
0x1e62  stelem.ref
0x1e63  dup
0x1e64  ldc.i4.1
0x1e65  ldloc.1
0x1e66  stelem.ref
0x1e67  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0x1e6c  leave.s  loc_1EB1
0x1e6e  stloc.2
0x1e6f  ldstr    aCouldNotKillPr// "Could not kill process because it is no"...
0x1e74  ldc.i4.2
0x1e75  newarr   [mscorlib]System.Object
0x1e7a  dup
0x1e7b  ldc.i4.0
0x1e7c  ldarg.0
0x1e7d  ldfld    class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::_processConfig
0x1e82  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Name()
0x1e87  stelem.ref
0x1e88  dup
0x1e89  ldc.i4.1
0x1e8a  ldloc.2
0x1e8b  stelem.ref
0x1e8c  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Warning(string, object[])
0x1e91  leave.s  loc_1EB1
0x1e93  ldstr    aProcessHasAlre// "Process has already exited: {0}"
0x1e98  ldc.i4.1
0x1e99  newarr   [mscorlib]System.Object
0x1e9e  dup
0x1e9f  ldc.i4.0
0x1ea0  ldarg.0
0x1ea1  call     instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::get_ProcessConfig()
0x1ea6  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Name()
0x1eab  stelem.ref
0x1eac  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x1eb1  ldarg.0
0x1eb2  ldnull
0x1eb3  stfld    class [System]System.Diagnostics.Process Microsoft.BIServer.BIService.ManagedProcess::_process
0x1eb8  ret
0x1eb9  ldstr    aAttemptingToKi// "Attempting to kill an unstarted process"...
0x1ebe  ldc.i4.1
0x1ebf  newarr   [mscorlib]System.Object
0x1ec4  dup
0x1ec5  ldc.i4.0
0x1ec6  ldarg.0
0x1ec7  call     instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::get_ProcessConfig()
0x1ecc  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Name()
0x1ed1  stelem.ref
0x1ed2  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Warning(string, object[])
0x1ed7  ret
```
