# Microsoft.VisualStudio.Setup.CompositionRoot::CreateAuthenticationProxy

- ea: `0x2440`
- end: `0x2475`
- name: `Microsoft.VisualStudio.Setup.CompositionRoot::CreateAuthenticationProxy`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4de0`

## callees

- `0x2440`

## pseudocode

```c

```

## disassembly

```asm
0x2440  ldarg.0
0x2441  ldarg.0
0x2442  ldc.i4.0
0x2443  call     T0x2B000034
0x2448  dup
0x2449  brtrue.s loc_2458
0x244b  pop
0x244c  ldarg.0
0x244d  ldc.i4.1
0x244e  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x2453  call     class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IAuthenticationProvider [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.Authentication.AuthenticationProviderFactory::Create(class [mscorlib]System.IServiceProvider, bool, native int)
0x2458  ldarg.1
0x2459  newobj   instance void [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.EnvironmentFacade::.ctor()
0x245e  ldarg.0
0x245f  ldc.i4.0
0x2460  call     T0x2B000035
0x2465  dup
0x2466  brtrue.s loc_246F
0x2468  pop
0x2469  ldarg.0
0x246a  newobj   instance void [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.WebRequestService::.ctor(class [mscorlib]System.IServiceProvider)
0x246f  newobj   instance void [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.DownloadManagerAuthenticationProxy::.ctor(class [mscorlib]System.IServiceProvider, class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IAuthenticationProvider, class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IDownloadManager, class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IEnvironment, class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IWebRequestService)
0x2474  ret
```
