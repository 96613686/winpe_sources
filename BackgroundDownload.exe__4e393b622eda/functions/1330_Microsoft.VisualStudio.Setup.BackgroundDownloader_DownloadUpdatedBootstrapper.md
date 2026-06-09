# Microsoft.VisualStudio.Setup.BackgroundDownloader::DownloadUpdatedBootstrapper

- ea: `0x1330`
- end: `0x138a`
- name: `Microsoft.VisualStudio.Setup.BackgroundDownloader::DownloadUpdatedBootstrapper`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0xdf0`

## callees

- `0x1330`
- `0x18d0`
- `0x3a90`

## pseudocode

```c

```

## disassembly

```asm
0x1330  newobj   instance void <>c__DisplayClass21_0::.ctor()
0x1335  stloc.0
0x1336  ldloc.0
0x1337  ldarg.3
0x1338  stfld    valuetype [mscorlib]System.Threading.CancellationToken <>c__DisplayClass21_0::cancellationToken
0x133d  ldloc.0
0x133e  ldarg.0
0x133f  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Services()
0x1344  ldarg.1
0x1345  newobj   instance void [System]System.Uri::.ctor(string)
0x134a  ldarg.2
0x134b  ldc.i4.1
0x134c  ldnull
0x134d  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::.ctor(class [mscorlib]System.IServiceProvider, class [System]System.Uri, class [mscorlib]System.Version, bool, string)
0x1352  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader <>c__DisplayClass21_0::bootstrapperDownloader
0x1357  ldloc.0
0x1358  ldftn    instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation> <>c__DisplayClass21_0::<DownloadUpdatedBootstrapper>b__0()
0x135e  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation>>::.ctor(object, native int)
0x1363  call     T0x2B00000C
0x1368  dup
0x1369  ldloc.0
0x136a  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <>c__DisplayClass21_0::cancellationToken
0x136f  callvirt instance void [mscorlib]System.Threading.Tasks.Task::Wait(valuetype [mscorlib]System.Threading.CancellationToken)
0x1374  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation>::get_Result()
0x1379  dup
0x137a  brtrue.s loc_1389
0x137c  pop
0x137d  ldloc.0
0x137e  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader <>c__DisplayClass21_0::bootstrapperDownloader
0x1383  ldarg.2
0x1384  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::GetCached(class [mscorlib]System.Version)
0x1389  ret
```
