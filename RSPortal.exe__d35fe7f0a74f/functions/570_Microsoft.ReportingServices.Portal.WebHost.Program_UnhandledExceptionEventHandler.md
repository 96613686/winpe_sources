# Microsoft.ReportingServices.Portal.WebHost.Program::UnhandledExceptionEventHandler

- ea: `0x570`
- end: `0x594`
- name: `Microsoft.ReportingServices.Portal.WebHost.Program::UnhandledExceptionEventHandler`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x570  ldstr    aUnhandledExcep// "Unhandled exception: {0}."
0x575  ldc.i4.1
0x576  newarr   [mscorlib]System.Object
0x57b  dup
0x57c  ldc.i4.0
0x57d  ldarg.1
0x57e  callvirt instance object [mscorlib]System.UnhandledExceptionEventArgs::get_ExceptionObject()
0x583  stelem.ref
0x584  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0x589  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x58e  callvirt instance void [System]System.Diagnostics.Process::Kill()
0x593  ret
```
