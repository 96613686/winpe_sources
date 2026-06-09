# <InitializeRemoteSettingsAsync>d__55::MoveNext

- ea: `0x4860`
- end: `0x4c62`
- name: `<InitializeRemoteSettingsAsync>d__55::MoveNext`
- size: `1026`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1860`
- `0x1870`
- `0x1880`
- `0x18d0`
- `0x4860`

## pseudocode

```c

```

## disassembly

```asm
0x4860  ldarg.0
0x4861  ldfld    int32 <InitializeRemoteSettingsAsync>d__55::<>1__state
0x4866  stloc.0
0x4867  ldarg.0
0x4868  ldfld    class Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase <InitializeRemoteSettingsAsync>d__55::<>4__this
0x486d  stloc.1
0x486e  ldloc.0
0x486f  switch   loc_48F0, loc_496E, loc_49EE, loc_4A71, loc_4AF4, loc_4B77, loc_4BF7
0x4890  ldarg.0
0x4891  ldloc.1
0x4892  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Services()
0x4897  ldc.i4.0
0x4898  call     T0x2B000054
0x489d  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRemoteSettingsService <InitializeRemoteSettingsAsync>d__55::<remoteSettingsService>5__2
0x48a2  ldarg.0
0x48a3  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRemoteSettingsService <InitializeRemoteSettingsAsync>d__55::<remoteSettingsService>5__2
0x48a8  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::FeaturesPath
0x48ad  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::BackgroundDownload
0x48b2  ldc.i4.1
0x48b3  ldarg.0
0x48b4  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InitializeRemoteSettingsAsync>d__55::cancellationToken
0x48b9  callvirt T0x2B000055
0x48be  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x48c3  stloc.3
0x48c4  ldloca.s 3
0x48c6  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x48cb  brtrue.s loc_490C
0x48cd  ldarg.0
0x48ce  ldc.i4.0
0x48cf  dup
0x48d0  stloc.0
0x48d1  stfld    int32 <InitializeRemoteSettingsAsync>d__55::<>1__state
0x48d6  ldarg.0
0x48d7  ldloc.3
0x48d8  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <InitializeRemoteSettingsAsync>d__55::<>u__1
0x48dd  ldarg.0
0x48de  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeRemoteSettingsAsync>d__55::<>t__builder
0x48e3  ldloca.s 3
0x48e5  ldarg.0
0x48e6  call     T0x2B000056
0x48eb  leave    loc_4C61
0x48f0  ldarg.0
0x48f1  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <InitializeRemoteSettingsAsync>d__55::<>u__1
0x48f6  stloc.3
0x48f7  ldarg.0
0x48f8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <InitializeRemoteSettingsAsync>d__55::<>u__1
0x48fd  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x4903  ldarg.0
0x4904  ldc.i4.m1
0x4905  dup
0x4906  stloc.0
0x4907  stfld    int32 <InitializeRemoteSettingsAsync>d__55::<>1__state
0x490c  ldloca.s 3
0x490e  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x4913  stloc.2
0x4914  ldloc.1
0x4915  ldloc.2
0x4916  call     instance void Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::set_FeatureEnabled(bool value)
0x491b  ldarg.0
0x491c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRemoteSettingsService <InitializeRemoteSettingsAsync>d__55::<remoteSettingsService>5__2
0x4921  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::FeaturesPath
0x4926  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::BackgroundDownload
0x492b  ldloc.1
0x492c  call     instance bool Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_DefaultUserEnabled()
0x4931  ldarg.0
0x4932  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InitializeRemoteSettingsAsync>d__55::cancellationToken
0x4937  callvirt T0x2B000055
0x493c  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x4941  stloc.3
0x4942  ldloca.s 3
0x4944  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x4949  brtrue.s loc_498A
0x494b  ldarg.0
0x494c  ldc.i4.1
0x494d  dup
0x494e  stloc.0
0x494f  stfld    int32 <InitializeRemoteSettingsAsync>d__55::<>1__state
0x4954  ldarg.0
0x4955  ldloc.3
0x4956  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <InitializeRemoteSettingsAsync>d__55::<>u__1
0x495b  ldarg.0
0x495c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeRemoteSettingsAsync>d__55::<>t__builder
0x4961  ldloca.s 3
0x4963  ldarg.0
0x4964  call     T0x2B000056
0x4969  leave    loc_4C61
0x496e  ldarg.0
0x496f  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <InitializeRemoteSettingsAsync>d__55::<>u__1
0x4974  stloc.3
0x4975  ldarg.0
0x4976  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <InitializeRemoteSettingsAsync>d__55::<>u__1
0x497b  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x4981  ldarg.0
0x4982  ldc.i4.m1
0x4983  dup
0x4984  stloc.0
0x4985  stfld    int32 <InitializeRemoteSettingsAsync>d__55::<>1__state
0x498a  ldloca.s 3
0x498c  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x4991  stloc.2
0x4992  ldloc.1
0x4993  ldloc.2
0x4994  call     instance void Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::set_DefaultUserEnabled(bool value)
0x4999  ldarg.0
0x499a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRemoteSettingsService <InitializeRemoteSettingsAsync>d__55::<remoteSettingsService>5__2
0x499f  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::VariablesPath
0x49a4  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::SuccessLogLimit
0x49a9  ldloc.1
0x49aa  ldfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::successLogLimit
0x49af  ldarg.0
0x49b0  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InitializeRemoteSettingsAsync>d__55::cancellationToken
0x49b5  callvirt T0x2B000057
0x49ba  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0x49bf  stloc.s  5
0x49c1  ldloca.s 5
0x49c3  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0x49c8  brtrue.s loc_4A0B
0x49ca  ldarg.0
0x49cb  ldc.i4.2
0x49cc  dup
0x49cd  stloc.0
0x49ce  stfld    int32 <InitializeRemoteSettingsAsync>d__55::<>1__state
0x49d3  ldarg.0
0x49d4  ldloc.s  5
0x49d6  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <InitializeRemoteSettingsAsync>d__55::<>u__2
0x49db  ldarg.0
0x49dc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeRemoteSettingsAsync>d__55::<>t__builder
0x49e1  ldloca.s 5
0x49e3  ldarg.0
0x49e4  call     T0x2B000058
0x49e9  leave    loc_4C61
0x49ee  ldarg.0
0x49ef  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <InitializeRemoteSettingsAsync>d__55::<>u__2
0x49f4  stloc.s  5
0x49f6  ldarg.0
0x49f7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <InitializeRemoteSettingsAsync>d__55::<>u__2
0x49fc  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>
0x4a02  ldarg.0
0x4a03  ldc.i4.m1
0x4a04  dup
0x4a05  stloc.0
0x4a06  stfld    int32 <InitializeRemoteSettingsAsync>d__55::<>1__state
0x4a0b  ldloca.s 5
0x4a0d  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::GetResult()
0x4a12  stloc.s  4
0x4a14  ldloc.1
0x4a15  ldloc.s  4
0x4a17  stfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::successLogLimit
0x4a1c  ldarg.0
0x4a1d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRemoteSettingsService <InitializeRemoteSettingsAsync>d__55::<remoteSettingsService>5__2
0x4a22  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::VariablesPath
0x4a27  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::ErrorLogLimit
0x4a2c  ldloc.1
0x4a2d  ldfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::errorLogLimit
0x4a32  ldarg.0
0x4a33  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InitializeRemoteSettingsAsync>d__55::cancellationToken
0x4a38  callvirt T0x2B000057
0x4a3d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0x4a42  stloc.s  5
0x4a44  ldloca.s 5
0x4a46  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0x4a4b  brtrue.s loc_4A8E
0x4a4d  ldarg.0
0x4a4e  ldc.i4.3
0x4a4f  dup
0x4a50  stloc.0
0x4a51  stfld    int32 <InitializeRemoteSettingsAsync>d__55::<>1__state
0x4a56  ldarg.0
0x4a57  ldloc.s  5
0x4a59  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <InitializeRemoteSettingsAsync>d__55::<>u__2
0x4a5e  ldarg.0
0x4a5f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeRemoteSettingsAsync>d__55::<>t__builder
0x4a64  ldloca.s 5
0x4a66  ldarg.0
0x4a67  call     T0x2B000058
0x4a6c  leave    loc_4C61
0x4a71  ldarg.0
0x4a72  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <InitializeRemoteSettingsAsync>d__55::<>u__2
0x4a77  stloc.s  5
0x4a79  ldarg.0
0x4a7a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <InitializeRemoteSettingsAsync>d__55::<>u__2
0x4a7f  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>
0x4a85  ldarg.0
0x4a86  ldc.i4.m1
0x4a87  dup
0x4a88  stloc.0
0x4a89  stfld    int32 <InitializeRemoteSettingsAsync>d__55::<>1__state
0x4a8e  ldloca.s 5
0x4a90  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::GetResult()
0x4a95  stloc.s  4
0x4a97  ldloc.1
0x4a98  ldloc.s  4
0x4a9a  stfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::errorLogLimit
0x4a9f  ldarg.0
0x4aa0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRemoteSettingsService <InitializeRemoteSettingsAsync>d__55::<remoteSettingsService>5__2
0x4aa5  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::VariablesPath
0x4aaa  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::CancelLogLimit
0x4aaf  ldloc.1
0x4ab0  ldfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::cancelLogLimit
0x4ab5  ldarg.0
0x4ab6  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InitializeRemoteSettingsAsync>d__55::cancellationToken
0x4abb  callvirt T0x2B000057
0x4ac0  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0x4ac5  stloc.s  5
0x4ac7  ldloca.s 5
0x4ac9  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0x4ace  brtrue.s loc_4B11
0x4ad0  ldarg.0
0x4ad1  ldc.i4.4
0x4ad2  dup
0x4ad3  stloc.0
0x4ad4  stfld    int32 <InitializeRemoteSettingsAsync>d__55::<>1__state
0x4ad9  ldarg.0
0x4ada  ldloc.s  5
0x4adc  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <InitializeRemoteSettingsAsync>d__55::<>u__2
0x4ae1  ldarg.0
0x4ae2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeRemoteSettingsAsync>d__55::<>t__builder
0x4ae7  ldloca.s 5
0x4ae9  ldarg.0
0x4aea  call     T0x2B000058
0x4aef  leave    loc_4C61
0x4af4  ldarg.0
0x4af5  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <InitializeRemoteSettingsAsync>d__55::<>u__2
0x4afa  stloc.s  5
0x4afc  ldarg.0
0x4afd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <InitializeRemoteSettingsAsync>d__55::<>u__2
0x4b02  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>
0x4b08  ldarg.0
0x4b09  ldc.i4.m1
0x4b0a  dup
0x4b0b  stloc.0
0x4b0c  stfld    int32 <InitializeRemoteSettingsAsync>d__55::<>1__state
0x4b11  ldloca.s 5
0x4b13  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::GetResult()
0x4b18  stloc.s  4
0x4b1a  ldloc.1
0x4b1b  ldloc.s  4
0x4b1d  stfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::cancelLogLimit
0x4b22  ldarg.0
0x4b23  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRemoteSettingsService <InitializeRemoteSettingsAsync>d__55::<remoteSettingsService>5__2
0x4b28  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::VariablesPath
0x4b2d  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::PrecheckFailureLogLimit
0x4b32  ldloc.1
0x4b33  ldfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::precheckFailureLogLimit
0x4b38  ldarg.0
0x4b39  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InitializeRemoteSettingsAsync>d__55::cancellationToken
0x4b3e  callvirt T0x2B000057
0x4b43  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0x4b48  stloc.s  5
0x4b4a  ldloca.s 5
0x4b4c  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0x4b51  brtrue.s loc_4B94
0x4b53  ldarg.0
0x4b54  ldc.i4.5
0x4b55  dup
0x4b56  stloc.0
0x4b57  stfld    int32 <InitializeRemoteSettingsAsync>d__55::<>1__state
0x4b5c  ldarg.0
0x4b5d  ldloc.s  5
0x4b5f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <InitializeRemoteSettingsAsync>d__55::<>u__2
0x4b64  ldarg.0
0x4b65  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeRemoteSettingsAsync>d__55::<>t__builder
0x4b6a  ldloca.s 5
0x4b6c  ldarg.0
0x4b6d  call     T0x2B000058
0x4b72  leave    loc_4C61
0x4b77  ldarg.0
0x4b78  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <InitializeRemoteSettingsAsync>d__55::<>u__2
0x4b7d  stloc.s  5
0x4b7f  ldarg.0
0x4b80  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <InitializeRemoteSettingsAsync>d__55::<>u__2
0x4b85  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>
0x4b8b  ldarg.0
0x4b8c  ldc.i4.m1
0x4b8d  dup
0x4b8e  stloc.0
0x4b8f  stfld    int32 <InitializeRemoteSettingsAsync>d__55::<>1__state
0x4b94  ldloca.s 5
0x4b96  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::GetResult()
0x4b9b  stloc.s  4
0x4b9d  ldloc.1
0x4b9e  ldloc.s  4
0x4ba0  stfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::precheckFailureLogLimit
0x4ba5  ldarg.0
0x4ba6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRemoteSettingsService <InitializeRemoteSettingsAsync>d__55::<remoteSettingsService>5__2
0x4bab  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::VariablesPath
0x4bb0  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::UpdateCheckOnlyFailureLogLimit
0x4bb5  ldloc.1
0x4bb6  ldfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::updateCheckOnlyFailureLogLimit
0x4bbb  ldarg.0
0x4bbc  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InitializeRemoteSettingsAsync>d__55::cancellationToken
0x4bc1  callvirt T0x2B000057
0x4bc6  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0x4bcb  stloc.s  5
0x4bcd  ldloca.s 5
0x4bcf  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0x4bd4  brtrue.s loc_4C14
0x4bd6  ldarg.0
0x4bd7  ldc.i4.6
0x4bd8  dup
  ... truncated ...
```
