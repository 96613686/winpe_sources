# Microsoft.VisualStudio.Setup.CompositionRoot::AddUpdateCheckServices

- ea: `0x2320`
- end: `0x2398`
- name: `Microsoft.VisualStudio.Setup.CompositionRoot::AddUpdateCheckServices`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x5090`

## callees

- `0x2a70`
- `0x37c0`

## string_xrefs

- `0x233b`: `Local\VsUpdateChecker`

## pseudocode

```c

```

## disassembly

```asm
0x2320  ldarg.0
0x2321  ldarg.0
0x2322  ldc.i4.1
0x2323  ldc.i4.1
0x2324  ldc.i4.0
0x2325  conv.i
0x2326  call     class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IDownloadManager [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadManagerFactory::Create(class [mscorlib]System.IServiceProvider, bool, bool, native int)
0x232b  ldc.i4.0
0x232c  ldc.i4.0
0x232d  callvirt T0x2B00002B
0x2332  ldarg.0
0x2333  ldc.i4.0
0x2334  call     T0x2B000011
0x2339  stloc.0
0x233a  ldarg.0
0x233b  ldstr    aLocalVsupdatec// "Local\\VsUpdateChecker"
0x2340  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.NullStopSignal::.ctor()
0x2345  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.MutexService::.ctor()
0x234a  ldloc.0
0x234b  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.SingletonService::.ctor(string, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IStopSignal, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IMutexService, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger)
0x2350  ldc.i4.0
0x2351  ldc.i4.0
0x2352  callvirt T0x2B00002C
0x2357  ldarg.0
0x2358  ldarg.0
0x2359  ldnull
0x235a  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ChannelManager::.ctor(class [mscorlib]System.IServiceProvider, string)
0x235f  ldc.i4.0
0x2360  ldc.i4.0
0x2361  callvirt T0x2B00002D
0x2366  ldarg.0
0x2367  ldarg.0
0x2368  ldc.i4.1
0x2369  call     T0x2B00002E
0x236e  ldarg.0
0x236f  ldc.i4.0
0x2370  call     T0x2B000011
0x2375  newobj   instance void Microsoft.VisualStudio.Setup.Services.StopSignalCancellationService::.ctor(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IStopSignal stopSignal, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x237a  ldc.i4.0
0x237b  ldc.i4.0
0x237c  callvirt T0x2B00002F
0x2381  ldarg.0
0x2382  ldarg.0
0x2383  ldarg.1
0x2384  ldarg.0
0x2385  ldc.i4.1
0x2386  call     T0x2B000030
0x238b  newobj   instance void Microsoft.VisualStudio.Setup.UpdateChecker::.ctor(class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.CommandLine commandLine, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ISingletonService singletonService)
0x2390  ldc.i4.0
0x2391  ldc.i4.0
0x2392  callvirt T0x2B000031
0x2397  ret
```
