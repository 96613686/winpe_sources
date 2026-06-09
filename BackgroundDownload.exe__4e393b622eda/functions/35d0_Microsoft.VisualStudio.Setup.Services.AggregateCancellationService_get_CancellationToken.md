# Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::get_CancellationToken

- ea: `0x35d0`
- end: `0x35dc`
- name: `Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::get_CancellationToken`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x35d0  ldarg.0
0x35d1  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::cancellationTokenSource
0x35d6  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x35db  ret
```
