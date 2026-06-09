# Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::get_CancellationToken

- ea: `0x3840`
- end: `0x384c`
- name: `Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::get_CancellationToken`
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
0x3840  ldarg.0
0x3841  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::cancellationTokenSource
0x3846  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x384b  ret
```
