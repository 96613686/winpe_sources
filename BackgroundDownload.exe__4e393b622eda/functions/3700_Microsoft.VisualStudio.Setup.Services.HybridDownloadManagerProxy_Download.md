# Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::Download

- ea: `0x3700`
- end: `0x3715`
- name: `Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::Download`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x36e0`

## pseudocode

```c

```

## disassembly

```asm
0x3700  ldarg.0
0x3701  call     instance class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IDownloadManager Microsoft.VisualStudio.Setup.Services.HybridDownloadManagerProxy::get_CurrentDownloadManager()
0x3706  ldarg.1
0x3707  ldarg.2
0x3708  ldarg.3
0x3709  ldarg.s  4
0x370b  ldarg.s  5
0x370d  ldarg.s  6
0x370f  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadSummary> [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IDownloadManager::Download(class [System]System.Uri, class [mscorlib]System.IO.Stream, class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.ProgressUpdateCallback, valuetype [mscorlib]System.Threading.CancellationToken, class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadContext, bool)
0x3714  ret
```
