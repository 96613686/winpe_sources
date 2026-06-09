# Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::OnStopRequested

- ea: `0x3800`
- end: `0x383b`
- name: `Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::OnStopRequested`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x3800`

## pseudocode

```c

```

## disassembly

```asm
0x3800  ldarg.0
0x3801  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::cancellationTokenSource
0x3806  callvirt instance bool [mscorlib]System.Threading.CancellationTokenSource::get_IsCancellationRequested()
0x380b  brfalse.s loc_380E
0x380d  ret
0x380e  nop
0x380f  ldarg.0
0x3810  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::logger
0x3815  dup
0x3816  brtrue.s loc_381B
0x3818  pop
0x3819  br.s     loc_382A
0x381b  ldstr    aStopSignalRece// "Stop signal received. Cancelling backgr"...
0x3820  call     T0x2B00000A
0x3825  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x382a  ldarg.0
0x382b  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::cancellationTokenSource
0x3830  callvirt instance void [mscorlib]System.Threading.CancellationTokenSource::Cancel()
0x3835  leave.s  loc_383A
0x3837  pop
0x3838  leave.s  loc_383A
0x383a  ret
```
