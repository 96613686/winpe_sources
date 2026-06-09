# Microsoft.BIServer.BIService.ManagedProcess::ProcessExitedHandler

- ea: `0x2000`
- end: `0x2025`
- name: `Microsoft.BIServer.BIService.ManagedProcess::ProcessExitedHandler`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1bd0`
- `0x1ee0`
- `0x20d0`

## pseudocode

```c

```

## disassembly

```asm
0x2000  ldstr    aChildProcess0D// "Child Process [{0}] Died. Check the log"...
0x2005  ldc.i4.1
0x2006  newarr   [mscorlib]System.Object
0x200b  dup
0x200c  ldc.i4.0
0x200d  ldarg.0
0x200e  call     instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::get_ProcessConfig()
0x2013  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Name()
0x2018  stelem.ref
0x2019  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Warning(string, object[])
0x201e  ldarg.0
0x201f  call     instance void Microsoft.BIServer.BIService.ManagedProcess::ThrottledStart()
0x2024  ret
```
