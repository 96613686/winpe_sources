# Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::OnUserIdleStateChanged

- ea: `0x3720`
- end: `0x372f`
- name: `Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::OnUserIdleStateChanged`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2d40`

## pseudocode

```c

```

## disassembly

```asm
0x3720  ldarg.0
0x3721  ldarg.2
0x3722  callvirt instance bool Microsoft.VisualStudio.Setup.UserIdleStateChangedEventArgs::get_IsIdle()
0x3727  volatile.
0x3729  stfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::isIdle
0x372e  ret
```
