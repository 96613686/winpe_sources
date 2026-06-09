# Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::Start

- ea: `0x2a50`
- end: `0x2a95`
- name: `Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::Start`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ac0`
- `0x2970`
- `0x2a50`
- `0x2aa0`

## string_xrefs

- `0x2a6b`: `Process not started (may already be running): {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2a50  ldarg.0
0x2a51  ldarg.0
0x2a52  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_workspacesRootPath
0x2a57  call     instance void Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::GenerateAsConfigurationFile(string workspacePath)
0x2a5c  ldarg.0
0x2a5d  call     instance class [System]System.Diagnostics.Process Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::CreateProcess()
0x2a62  stloc.0
0x2a63  ldloc.0
0x2a64  callvirt instance bool [System]System.Diagnostics.Process::Start()
0x2a69  brtrue.s loc_2A88
0x2a6b  ldstr    aProcessNotStar// "Process not started (may already be run"...
0x2a70  ldc.i4.1
0x2a71  newarr   [mscorlib]System.Object
0x2a76  dup
0x2a77  ldc.i4.0
0x2a78  ldarg.0
0x2a79  callvirt instance string [mscorlib]System.Object::ToString()
0x2a7e  stelem.ref
0x2a7f  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0x2a84  ldnull
0x2a85  stloc.0
0x2a86  br.s     loc_2A93
0x2a88  ldloc.0
0x2a89  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x2a8e  call     void Microsoft.BIServer.BIService.ProcessBinder::Bind(int32 processId)
0x2a93  ldloc.0
0x2a94  ret
```
