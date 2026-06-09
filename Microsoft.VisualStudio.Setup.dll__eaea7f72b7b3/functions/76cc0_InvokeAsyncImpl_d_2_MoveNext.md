# <InvokeAsyncImpl>d__2::MoveNext

- ea: `0x76cc0`
- end: `0x76efa`
- name: `<InvokeAsyncImpl>d__2::MoveNext`
- size: `570`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4b730`
- `0x4b780`
- `0x4bc50`
- `0x4bf10`
- `0x4c750`
- `0x76c90`
- `0x76cc0`

## string_xrefs

- `0x76d77`: `Starting product repair.`
- `0x76ea1`: `Completed product repair.`

## pseudocode

```c

```

## disassembly

```asm
0x76cc0  ldarg.0
0x76cc1  ldfld    int32 <InvokeAsyncImpl>d__2::<>1__state
0x76cc6  stloc.0
0x76cc7  ldarg.0
0x76cc8  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductRepairer <InvokeAsyncImpl>d__2::<>4__this
0x76ccd  stloc.1
0x76cce  ldloc.0
0x76ccf  switch   loc_76D40, loc_76DDC, loc_76E71
0x76ce0  ldarg.0
0x76ce1  newobj   instance void <>c__DisplayClass2_0::.ctor()
0x76ce6  stfld    class <>c__DisplayClass2_0 <InvokeAsyncImpl>d__2::<>8__1
0x76ceb  ldarg.0
0x76cec  ldfld    class <>c__DisplayClass2_0 <InvokeAsyncImpl>d__2::<>8__1
0x76cf1  ldarg.0
0x76cf2  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InvokeAsyncImpl>d__2::token
0x76cf7  stfld    valuetype [mscorlib]System.Threading.CancellationToken <>c__DisplayClass2_0::token
0x76cfc  ldloc.1
0x76cfd  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product> Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::GetRegisteredInstanceProductAsync()
0x76d02  ldc.i4.0
0x76d03  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product>::ConfigureAwait(!!T0)
0x76d08  stloc.s  5
0x76d0a  ldloca.s 5
0x76d0c  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product>::GetAwaiter()
0x76d11  stloc.s  4
0x76d13  ldloca.s 4
0x76d15  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product>::get_IsCompleted()
0x76d1a  brtrue.s loc_76D5D
0x76d1c  ldarg.0
0x76d1d  ldc.i4.0
0x76d1e  dup
0x76d1f  stloc.0
0x76d20  stfld    int32 <InvokeAsyncImpl>d__2::<>1__state
0x76d25  ldarg.0
0x76d26  ldloc.s  4
0x76d28  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product> <InvokeAsyncImpl>d__2::<>u__1
0x76d2d  ldarg.0
0x76d2e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__2::<>t__builder
0x76d33  ldloca.s 4
0x76d35  ldarg.0
0x76d36  call     T0x2B000369
0x76d3b  leave    loc_76EF9
0x76d40  ldarg.0
0x76d41  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product> <InvokeAsyncImpl>d__2::<>u__1
0x76d46  stloc.s  4
0x76d48  ldarg.0
0x76d49  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product> <InvokeAsyncImpl>d__2::<>u__1
0x76d4e  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product>
0x76d54  ldarg.0
0x76d55  ldc.i4.m1
0x76d56  dup
0x76d57  stloc.0
0x76d58  stfld    int32 <InvokeAsyncImpl>d__2::<>1__state
0x76d5d  ldloca.s 4
0x76d5f  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product>::GetResult()
0x76d64  stloc.3
0x76d65  ldloc.3
0x76d66  brfalse  loc_76EB3
0x76d6b  ldloc.1
0x76d6c  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::get_Logger()
0x76d71  dup
0x76d72  brtrue.s loc_76D77
0x76d74  pop
0x76d75  br.s     loc_76D86
0x76d77  ldstr    aStartingProduc_0// "Starting product repair."
0x76d7c  call     T0x2B000003
0x76d81  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x76d86  ldarg.0
0x76d87  ldfld    class <>c__DisplayClass2_0 <InvokeAsyncImpl>d__2::<>8__1
0x76d8c  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <>c__DisplayClass2_0::token
0x76d91  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x76d96  ldloc.1
0x76d97  ldloc.3
0x76d98  ldc.i4.1
0x76d99  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph> Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::GetDependencyGraphWithSelectionAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Product product, bool overwrite)
0x76d9e  ldc.i4.0
0x76d9f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph>::ConfigureAwait(!!T0)
0x76da4  stloc.s  7
0x76da6  ldloca.s 7
0x76da8  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph>::GetAwaiter()
0x76dad  stloc.s  6
0x76daf  ldloca.s 6
0x76db1  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph>::get_IsCompleted()
0x76db6  brtrue.s loc_76DF9
0x76db8  ldarg.0
0x76db9  ldc.i4.1
0x76dba  dup
0x76dbb  stloc.0
0x76dbc  stfld    int32 <InvokeAsyncImpl>d__2::<>1__state
0x76dc1  ldarg.0
0x76dc2  ldloc.s  6
0x76dc4  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph> <InvokeAsyncImpl>d__2::<>u__2
0x76dc9  ldarg.0
0x76dca  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__2::<>t__builder
0x76dcf  ldloca.s 6
0x76dd1  ldarg.0
0x76dd2  call     T0x2B00036A
0x76dd7  leave    loc_76EF9
0x76ddc  ldarg.0
0x76ddd  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph> <InvokeAsyncImpl>d__2::<>u__2
0x76de2  stloc.s  6
0x76de4  ldarg.0
0x76de5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph> <InvokeAsyncImpl>d__2::<>u__2
0x76dea  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph>
0x76df0  ldarg.0
0x76df1  ldc.i4.m1
0x76df2  dup
0x76df3  stloc.0
0x76df4  stfld    int32 <InvokeAsyncImpl>d__2::<>1__state
0x76df9  ldloca.s 6
0x76dfb  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph>::GetResult()
0x76e00  pop
0x76e01  ldarg.0
0x76e02  ldfld    class <>c__DisplayClass2_0 <InvokeAsyncImpl>d__2::<>8__1
0x76e07  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <>c__DisplayClass2_0::token
0x76e0c  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x76e11  ldloc.1
0x76e12  ldloc.1
0x76e13  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductRepairerOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductRepairer::options
0x76e18  callvirt instance valuetype Microsoft.VisualStudio.Setup.TelemetryContext Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions::get_TelemetryContext()
0x76e1d  ldarg.0
0x76e1e  ldfld    class <>c__DisplayClass2_0 <InvokeAsyncImpl>d__2::<>8__1
0x76e23  ldftn    instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance <>c__DisplayClass2_0::<InvokeAsyncImpl>b__0(class Microsoft.VisualStudio.Setup.IEngine)
0x76e29  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.IEngine, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::.ctor(object, native int)
0x76e2e  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::InvokeEngineAsync(valuetype Microsoft.VisualStudio.Setup.TelemetryContext, class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.IEngine, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> telemetryContext)
0x76e33  ldc.i4.0
0x76e34  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::ConfigureAwait(!!T0)
0x76e39  stloc.s  9
0x76e3b  ldloca.s 9
0x76e3d  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::GetAwaiter()
0x76e42  stloc.s  8
0x76e44  ldloca.s 8
0x76e46  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::get_IsCompleted()
0x76e4b  brtrue.s loc_76E8E
0x76e4d  ldarg.0
0x76e4e  ldc.i4.2
0x76e4f  dup
0x76e50  stloc.0
0x76e51  stfld    int32 <InvokeAsyncImpl>d__2::<>1__state
0x76e56  ldarg.0
0x76e57  ldloc.s  8
0x76e59  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__2::<>u__3
0x76e5e  ldarg.0
0x76e5f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__2::<>t__builder
0x76e64  ldloca.s 8
0x76e66  ldarg.0
0x76e67  call     T0x2B00036B
0x76e6c  leave    loc_76EF9
0x76e71  ldarg.0
0x76e72  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__2::<>u__3
0x76e77  stloc.s  8
0x76e79  ldarg.0
0x76e7a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__2::<>u__3
0x76e7f  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>
0x76e85  ldarg.0
0x76e86  ldc.i4.m1
0x76e87  dup
0x76e88  stloc.0
0x76e89  stfld    int32 <InvokeAsyncImpl>d__2::<>1__state
0x76e8e  ldloca.s 8
0x76e90  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::GetResult()
0x76e95  ldloc.1
0x76e96  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::get_Logger()
0x76e9b  dup
0x76e9c  brtrue.s loc_76EA1
0x76e9e  pop
0x76e9f  br.s     loc_76EB0
0x76ea1  ldstr    aCompletedProdu_0// "Completed product repair."
0x76ea6  call     T0x2B000003
0x76eab  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x76eb0  stloc.2
0x76eb1  leave.s  loc_76EDE
0x76eb3  ldstr    aFailedToGetThe_7// "Failed to get the product reference"
0x76eb8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x76ebd  throw
0x76ebe  stloc.s  0xA
0x76ec0  ldarg.0
0x76ec1  ldc.i4.s 0xFE
0x76ec3  stfld    int32 <InvokeAsyncImpl>d__2::<>1__state
0x76ec8  ldarg.0
0x76ec9  ldnull
0x76eca  stfld    class <>c__DisplayClass2_0 <InvokeAsyncImpl>d__2::<>8__1
0x76ecf  ldarg.0
0x76ed0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__2::<>t__builder
0x76ed5  ldloc.s  0xA
0x76ed7  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::SetException(class [mscorlib]System.Exception)
0x76edc  leave.s  loc_76EF9
0x76ede  ldarg.0
0x76edf  ldc.i4.s 0xFE
0x76ee1  stfld    int32 <InvokeAsyncImpl>d__2::<>1__state
0x76ee6  ldarg.0
0x76ee7  ldnull
0x76ee8  stfld    class <>c__DisplayClass2_0 <InvokeAsyncImpl>d__2::<>8__1
0x76eed  ldarg.0
0x76eee  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> <InvokeAsyncImpl>d__2::<>t__builder
0x76ef3  ldloc.2
0x76ef4  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance>::SetResult(var<u1>)
0x76ef9  ret
```
