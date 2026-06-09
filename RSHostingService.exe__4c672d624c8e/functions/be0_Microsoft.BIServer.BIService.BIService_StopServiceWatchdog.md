# Microsoft.BIServer.BIService.BIService::StopServiceWatchdog

- ea: `0xbe0`
- end: `0xc0d`
- name: `Microsoft.BIServer.BIService.BIService::StopServiceWatchdog`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1080`

## callees

- `0xbe0`

## pseudocode

```c

```

## disassembly

```asm
0xbe0  ldarg.0
0xbe1  ldfld    class [mscorlib]System.Threading.Tasks.Task Microsoft.BIServer.BIService.BIService::_serviceWatchdogTask
0xbe6  brfalse.s loc_C0C
0xbe8  ldarg.0
0xbe9  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.BIServer.BIService.BIService::_serviceWatchdogCancellation
0xbee  callvirt instance void [mscorlib]System.Threading.CancellationTokenSource::Cancel()
0xbf3  ldarg.0
0xbf4  ldfld    class [mscorlib]System.Threading.Tasks.Task Microsoft.BIServer.BIService.BIService::_serviceWatchdogTask
0xbf9  callvirt instance void [mscorlib]System.Threading.Tasks.Task::Wait()
0xbfe  ldarg.0
0xbff  ldnull
0xc00  stfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.BIServer.BIService.BIService::_serviceWatchdogCancellation
0xc05  ldarg.0
0xc06  ldnull
0xc07  stfld    class [mscorlib]System.Threading.Tasks.Task Microsoft.BIServer.BIService.BIService::_serviceWatchdogTask
0xc0c  ret
```
