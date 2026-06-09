# Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::get_CancellationToken

- ea: `0x3970`
- end: `0x397c`
- name: `Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::get_CancellationToken`
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
0x3970  ldarg.0
0x3971  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::cancellationTokenSource
0x3976  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x397b  ret
```
