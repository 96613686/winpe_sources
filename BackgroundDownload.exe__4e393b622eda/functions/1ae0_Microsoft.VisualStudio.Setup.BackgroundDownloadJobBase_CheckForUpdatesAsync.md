# Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::CheckForUpdatesAsync

- ea: `0x1ae0`
- end: `0x1b05`
- name: `Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::CheckForUpdatesAsync`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3c10`
- `0x5530`

## callees

- `0x18d0`
- `0x1910`
- `0x1d10`
- `0x25e0`

## pseudocode

```c

```

## disassembly

```asm
0x1ae0  ldarg.1
0x1ae1  ldstr    aPrimarychild// "primaryChild"
0x1ae6  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x1aeb  ldarg.1
0x1aec  ldarg.0
0x1aed  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Services()
0x1af2  ldarg.2
0x1af3  ldarg.0
0x1af4  call     instance class Microsoft.VisualStudio.Setup.CommandLine Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_CommandLine()
0x1af9  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.CommandLine::get_InstallChannelUri()
0x1afe  ldarg.3
0x1aff  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.CheckForUpdatesResult> Microsoft.VisualStudio.Setup.IWork::CheckForUpdatesAsync(class [mscorlib]System.IServiceProvider services, string instanceId, class [System]System.Uri installChannelUri, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x1b04  ret
```
