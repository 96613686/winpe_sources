# <InvokeAsyncImpl>d__4::MoveNext_0

- ea: `0x769f0`
- end: `0x76c6e`
- name: `<InvokeAsyncImpl>d__4::MoveNext_0`
- size: `638`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4b6a0`
- `0x4b780`
- `0x4bc50`
- `0x4dd70`
- `0x76590`
- `0x769f0`

## string_xrefs

- `0x76b51`: `installationPath`
- `0x76c14`: `installationPath`
- `0x76c07`: `Completed product modification [{0}: "{1}"]`

## pseudocode

```c

```

## disassembly

```asm
0x769f0  ldarg.0
0x769f1  ldfld    int32 <InvokeAsyncImpl>d__4::<>1__state
0x769f6  stloc.0
0x769f7  ldarg.0
0x769f8  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductModifier <InvokeAsyncImpl>d__4::<>4__this
0x769fd  stloc.1
0x769fe  ldloc.0
0x769ff  switch   loc_76A87, loc_76B02, loc_76BD5
0x76a10  ldarg.0
0x76a11  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x76a16  stfld    class <>c__DisplayClass4_0 <InvokeAsyncImpl>d__4::<>8__1
0x76a1b  ldarg.0
0x76a1c  ldfld    class <>c__DisplayClass4_0 <InvokeAsyncImpl>d__4::<>8__1
0x76a21  ldarg.0
0x76a22  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductModifier <InvokeAsyncImpl>d__4::<>4__this
0x76a27  stfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductModifier <>c__DisplayClass4_0::<>4__this
0x76a2c  ldarg.0
0x76a2d  ldfld    class <>c__DisplayClass4_0 <InvokeAsyncImpl>d__4::<>8__1
0x76a32  ldarg.0
0x76a33  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InvokeAsyncImpl>d__4::token
0x76a38  stfld    valuetype [mscorlib]System.Threading.CancellationToken <>c__DisplayClass4_0::token
0x76a3d  ldloc.1
0x76a3e  ldloc.1
0x76a3f  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductModifierOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductModifier::options
0x76a44  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Services.Installer.ProductModifier::InitializeAsync(class Microsoft.VisualStudio.Setup.Services.Installer.ProductModifierOptions options)
0x76a49  ldc.i4.0
0x76a4a  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x76a4f  stloc.s  6
0x76a51  ldloca.s 6
0x76a53  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x76a58  stloc.s  5
0x76a5a  ldloca.s 5
0x76a5c  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x76a61  brtrue.s loc_76AA4
0x76a63  ldarg.0
0x76a64  ldc.i4.0
0x76a65  dup
0x76a66  stloc.0
0x76a67  stfld    int32 <InvokeAsyncImpl>d__4::<>1__state
0x76a6c  ldarg.0
0x76a6d  ldloc.s  5
0x76a6f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <InvokeAsyncImpl>d__4::<>u__1
0x76a74  ldarg.0
0x76a75  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__4::<>t__builder
0x76a7a  ldloca.s 5
0x76a7c  ldarg.0
0x76a7d  call     T0x2B000367
0x76a82  leave    loc_76C6D
0x76a87  ldarg.0
0x76a88  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <InvokeAsyncImpl>d__4::<>u__1
0x76a8d  stloc.s  5
0x76a8f  ldarg.0
0x76a90  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <InvokeAsyncImpl>d__4::<>u__1
0x76a95  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x76a9b  ldarg.0
0x76a9c  ldc.i4.m1
0x76a9d  dup
0x76a9e  stloc.0
0x76a9f  stfld    int32 <InvokeAsyncImpl>d__4::<>1__state
0x76aa4  ldloca.s 5
0x76aa6  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x76aab  ldloc.1
0x76aac  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product Microsoft.VisualStudio.Setup.Services.Installer.ProductModifier::product
0x76ab1  brtrue.s loc_76ABE
0x76ab3  ldstr    aCannotFindTheP// "Cannot find the product to modify"
0x76ab8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x76abd  throw
0x76abe  ldloc.1
0x76abf  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::GetInstanceAsync()
0x76ac4  ldc.i4.0
0x76ac5  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::ConfigureAwait(!!T0)
0x76aca  stloc.s  8
0x76acc  ldloca.s 8
0x76ace  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::GetAwaiter()
0x76ad3  stloc.s  7
0x76ad5  ldloca.s 7
0x76ad7  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::get_IsCompleted()
0x76adc  brtrue.s loc_76B1F
0x76ade  ldarg.0
0x76adf  ldc.i4.1
0x76ae0  dup
0x76ae1  stloc.0
0x76ae2  stfld    int32 <InvokeAsyncImpl>d__4::<>1__state
0x76ae7  ldarg.0
0x76ae8  ldloc.s  7
0x76aea  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__4::<>u__2
0x76aef  ldarg.0
0x76af0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__4::<>t__builder
0x76af5  ldloca.s 7
0x76af7  ldarg.0
0x76af8  call     T0x2B000368
0x76afd  leave    loc_76C6D
0x76b02  ldarg.0
0x76b03  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__4::<>u__2
0x76b08  stloc.s  7
0x76b0a  ldarg.0
0x76b0b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__4::<>u__2
0x76b10  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>
0x76b16  ldarg.0
0x76b17  ldc.i4.m1
0x76b18  dup
0x76b19  stloc.0
0x76b1a  stfld    int32 <InvokeAsyncImpl>d__4::<>1__state
0x76b1f  ldloca.s 7
0x76b21  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::GetResult()
0x76b26  stloc.3
0x76b27  ldarg.0
0x76b28  ldfld    class <>c__DisplayClass4_0 <InvokeAsyncImpl>d__4::<>8__1
0x76b2d  ldloc.3
0x76b2e  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_InstallationPath()
0x76b33  stfld    string <>c__DisplayClass4_0::installationPath
0x76b38  ldloc.1
0x76b39  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::get_Logger()
0x76b3e  dup
0x76b3f  brtrue.s loc_76B44
0x76b41  pop
0x76b42  br.s     loc_76B6A
0x76b44  ldstr    aStartingProduc// "Starting product modification [{0}: \"{"...
0x76b49  ldc.i4.2
0x76b4a  newarr   [mscorlib]System.Object
0x76b4f  dup
0x76b50  ldc.i4.0
0x76b51  ldstr    aInstallationpa// "installationPath"
0x76b56  stelem.ref
0x76b57  dup
0x76b58  ldc.i4.1
0x76b59  ldarg.0
0x76b5a  ldfld    class <>c__DisplayClass4_0 <InvokeAsyncImpl>d__4::<>8__1
0x76b5f  ldfld    string <>c__DisplayClass4_0::installationPath
0x76b64  stelem.ref
0x76b65  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x76b6a  ldarg.0
0x76b6b  ldfld    class <>c__DisplayClass4_0 <InvokeAsyncImpl>d__4::<>8__1
0x76b70  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <>c__DisplayClass4_0::token
0x76b75  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x76b7a  ldloc.1
0x76b7b  ldloc.1
0x76b7c  ldfld    valuetype Microsoft.VisualStudio.Setup.TelemetryContext Microsoft.VisualStudio.Setup.Services.Installer.ProductModifier::telemetryContext
0x76b81  ldarg.0
0x76b82  ldfld    class <>c__DisplayClass4_0 <InvokeAsyncImpl>d__4::<>8__1
0x76b87  ldftn    instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance <>c__DisplayClass4_0::<InvokeAsyncImpl>b__0(class Microsoft.VisualStudio.Setup.IEngine)
0x76b8d  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.IEngine, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::.ctor(object, native int)
0x76b92  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::InvokeEngineAsync(valuetype Microsoft.VisualStudio.Setup.TelemetryContext, class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.IEngine, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> telemetryContext)
0x76b97  ldc.i4.0
0x76b98  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::ConfigureAwait(!!T0)
0x76b9d  stloc.s  8
0x76b9f  ldloca.s 8
0x76ba1  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::GetAwaiter()
0x76ba6  stloc.s  7
0x76ba8  ldloca.s 7
0x76baa  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::get_IsCompleted()
0x76baf  brtrue.s loc_76BF2
0x76bb1  ldarg.0
0x76bb2  ldc.i4.2
0x76bb3  dup
0x76bb4  stloc.0
0x76bb5  stfld    int32 <InvokeAsyncImpl>d__4::<>1__state
0x76bba  ldarg.0
0x76bbb  ldloc.s  7
0x76bbd  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__4::<>u__2
0x76bc2  ldarg.0
0x76bc3  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__4::<>t__builder
0x76bc8  ldloca.s 7
0x76bca  ldarg.0
0x76bcb  call     T0x2B000368
0x76bd0  leave    loc_76C6D
0x76bd5  ldarg.0
0x76bd6  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__4::<>u__2
0x76bdb  stloc.s  7
0x76bdd  ldarg.0
0x76bde  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__4::<>u__2
0x76be3  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>
0x76be9  ldarg.0
0x76bea  ldc.i4.m1
0x76beb  dup
0x76bec  stloc.0
0x76bed  stfld    int32 <InvokeAsyncImpl>d__4::<>1__state
0x76bf2  ldloca.s 7
0x76bf4  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::GetResult()
0x76bf9  stloc.s  4
0x76bfb  ldloc.1
0x76bfc  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::get_Logger()
0x76c01  dup
0x76c02  brtrue.s loc_76C07
0x76c04  pop
0x76c05  br.s     loc_76C2D
0x76c07  ldstr    aCompletedProdu// "Completed product modification [{0}: \""...
0x76c0c  ldc.i4.2
0x76c0d  newarr   [mscorlib]System.Object
0x76c12  dup
0x76c13  ldc.i4.0
0x76c14  ldstr    aInstallationpa// "installationPath"
0x76c19  stelem.ref
0x76c1a  dup
0x76c1b  ldc.i4.1
0x76c1c  ldarg.0
0x76c1d  ldfld    class <>c__DisplayClass4_0 <InvokeAsyncImpl>d__4::<>8__1
0x76c22  ldfld    string <>c__DisplayClass4_0::installationPath
0x76c27  stelem.ref
0x76c28  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x76c2d  ldloc.s  4
0x76c2f  stloc.2
0x76c30  leave.s  loc_76C52
0x76c32  stloc.s  9
0x76c34  ldarg.0
0x76c35  ldc.i4.s 0xFE
0x76c37  stfld    int32 <InvokeAsyncImpl>d__4::<>1__state
0x76c3c  ldarg.0
0x76c3d  ldnull
0x76c3e  stfld    class <>c__DisplayClass4_0 <InvokeAsyncImpl>d__4::<>8__1
0x76c43  ldarg.0
0x76c44  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__4::<>t__builder
0x76c49  ldloc.s  9
0x76c4b  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::SetException(class [mscorlib]System.Exception)
0x76c50  leave.s  loc_76C6D
0x76c52  ldarg.0
0x76c53  ldc.i4.s 0xFE
0x76c55  stfld    int32 <InvokeAsyncImpl>d__4::<>1__state
0x76c5a  ldarg.0
0x76c5b  ldnull
0x76c5c  stfld    class <>c__DisplayClass4_0 <InvokeAsyncImpl>d__4::<>8__1
0x76c61  ldarg.0
0x76c62  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__4::<>t__builder
0x76c67  ldloc.2
0x76c68  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::SetResult(var<u1>)
0x76c6d  ret
```
