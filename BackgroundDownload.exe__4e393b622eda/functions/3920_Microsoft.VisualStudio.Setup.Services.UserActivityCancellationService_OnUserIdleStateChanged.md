# Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::OnUserIdleStateChanged

- ea: `0x3920`
- end: `0x3961`
- name: `Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::OnUserIdleStateChanged`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2d40`
- `0x3920`

## pseudocode

```c

```

## disassembly

```asm
0x3920  ldarg.2
0x3921  callvirt instance bool Microsoft.VisualStudio.Setup.UserIdleStateChangedEventArgs::get_IsIdle()
0x3926  brtrue.s loc_3960
0x3928  ldarg.0
0x3929  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::cancellationTokenSource
0x392e  callvirt instance bool [mscorlib]System.Threading.CancellationTokenSource::get_IsCancellationRequested()
0x3933  brtrue.s loc_3960
0x3935  ldarg.0
0x3936  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::logger
0x393b  dup
0x393c  brtrue.s loc_3941
0x393e  pop
0x393f  br.s     loc_3950
0x3941  ldstr    aUserActivityDe// "User activity detected. Cancelling back"...
0x3946  call     T0x2B00000A
0x394b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x3950  ldarg.0
0x3951  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Services.UserActivityCancellationService::cancellationTokenSource
0x3956  callvirt instance void [mscorlib]System.Threading.CancellationTokenSource::Cancel()
0x395b  leave.s  loc_3960
0x395d  pop
0x395e  leave.s  loc_3960
0x3960  ret
```
