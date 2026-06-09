# Microsoft.VisualStudio.Setup.CompositionRoot::AddBackgroundDownloadJob

- ea: `0x2480`
- end: `0x24b9`
- name: `Microsoft.VisualStudio.Setup.CompositionRoot::AddBackgroundDownloadJob`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4de0`

## callees

- `0xcb0`
- `0x1c30`
- `0x2d70`
- `0x2ed0`
- `0x3670`

## pseudocode

```c

```

## disassembly

```asm
0x2480  ldarg.1
0x2481  callvirt instance bool Microsoft.VisualStudio.Setup.CommandLine::get_IsChildProcess()
0x2486  call     class Microsoft.VisualStudio.Setup.IWork Microsoft.VisualStudio.Setup.WorkFactory::Create(bool isChildProcess)
0x248b  stloc.0
0x248c  ldarg.0
0x248d  ldc.i4.0
0x248e  call     T0x2B000011
0x2493  newobj   instance void Microsoft.VisualStudio.Setup.WMIValidator::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x2498  stloc.1
0x2499  ldarg.0
0x249a  ldc.i4.1
0x249b  call     T0x2B000036
0x24a0  stloc.2
0x24a1  ldarg.0
0x24a2  ldarg.0
0x24a3  ldarg.1
0x24a4  newobj   instance void Microsoft.VisualStudio.Setup.Services.AllInstancesProvider::.ctor()
0x24a9  ldloc.0
0x24aa  ldloc.1
0x24ab  ldloc.2
0x24ac  newobj   instance void Microsoft.VisualStudio.Setup.BackgroundDownloader::.ctor(class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.CommandLine commandLine, class Microsoft.VisualStudio.Setup.Services.IBackgroundDownloadInstanceProvider instanceProvider, class Microsoft.VisualStudio.Setup.IWork work, class Microsoft.VisualStudio.Setup.IWMIValidator wmiValidator, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IProgressReceiver progressReceiver)
0x24b1  ldc.i4.0
0x24b2  ldc.i4.0
0x24b3  callvirt T0x2B000031
0x24b8  ret
```
