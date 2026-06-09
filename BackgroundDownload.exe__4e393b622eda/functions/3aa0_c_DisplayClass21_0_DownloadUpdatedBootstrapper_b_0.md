# <>c__DisplayClass21_0::<DownloadUpdatedBootstrapper>b__0

- ea: `0x3aa0`
- end: `0x3ab2`
- name: `<>c__DisplayClass21_0::<DownloadUpdatedBootstrapper>b__0`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c

```

## disassembly

```asm
0x3aa0  ldarg.0
0x3aa1  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader <>c__DisplayClass21_0::bootstrapperDownloader
0x3aa6  ldarg.0
0x3aa7  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <>c__DisplayClass21_0::cancellationToken
0x3aac  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::DownloadAsync(valuetype [mscorlib]System.Threading.CancellationToken)
0x3ab1  ret
```
