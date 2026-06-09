# Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::get_CurrentDownloadManager

- ea: `0x36e0`
- end: `0x36f8`
- name: `Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::get_CurrentDownloadManager`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3700`

## callees

- `0x36e0`

## pseudocode

```c

```

## disassembly

```asm
0x36e0  ldarg.0
0x36e1  volatile.
0x36e3  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::isIdle
0x36e8  brtrue.s loc_36F1
0x36ea  ldarg.0
0x36eb  ldfld    class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IDownloadManager Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::activeDownloadManager
0x36f0  ret
0x36f1  ldarg.0
0x36f2  ldfld    class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IDownloadManager Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::idleDownloadManager
0x36f7  ret
```
