# Microsoft.BIServer.BIService.BIService::StartServiceWatchdog

- ea: `0xbb0`
- end: `0xbd3`
- name: `Microsoft.BIServer.BIService.BIService::StartServiceWatchdog`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2dd0`

## callees

- `0xc10`

## pseudocode

```c

```

## disassembly

```asm
0xbb0  ldarg.0
0xbb1  newobj   instance void [mscorlib]System.Threading.CancellationTokenSource::.ctor()
0xbb6  stfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.BIServer.BIService.BIService::_serviceWatchdogCancellation
0xbbb  ldarg.0
0xbbc  ldarg.0
0xbbd  ldarg.0
0xbbe  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.BIServer.BIService.BIService::_serviceWatchdogCancellation
0xbc3  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0xbc8  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.BIServer.BIService.BIService::ServiceWatchdog(valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0xbcd  stfld    class [mscorlib]System.Threading.Tasks.Task Microsoft.BIServer.BIService.BIService::_serviceWatchdogTask
0xbd2  ret
```
