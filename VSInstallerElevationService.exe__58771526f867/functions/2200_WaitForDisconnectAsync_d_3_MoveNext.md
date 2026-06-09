# <WaitForDisconnectAsync>d__3::MoveNext

- ea: `0x2200`
- end: `0x229b`
- name: `<WaitForDisconnectAsync>d__3::MoveNext`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x2200`

## pseudocode

```c

```

## disassembly

```asm
0x2200  ldarg.0
0x2201  ldfld    int32 <WaitForDisconnectAsync>d__3::<>1__state
0x2206  stloc.0
0x2207  ldarg.0
0x2208  ldfld    class Microsoft.VisualStudio.Setup.Services.RpcServiceFacade <WaitForDisconnectAsync>d__3::<>4__this
0x220d  stloc.1
0x220e  ldloc.0
0x220f  brfalse.s loc_224B
0x2211  ldloc.1
0x2212  ldfld    class [StreamJsonRpc]StreamJsonRpc.JsonRpc Microsoft.VisualStudio.Setup.Services.RpcServiceFacade::rpc
0x2217  callvirt instance class [mscorlib]System.Threading.Tasks.Task [StreamJsonRpc]StreamJsonRpc.JsonRpc::get_Completion()
0x221c  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x2221  stloc.2
0x2222  ldloca.s 2
0x2224  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x2229  brtrue.s loc_2267
0x222b  ldarg.0
0x222c  ldc.i4.0
0x222d  dup
0x222e  stloc.0
0x222f  stfld    int32 <WaitForDisconnectAsync>d__3::<>1__state
0x2234  ldarg.0
0x2235  ldloc.2
0x2236  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <WaitForDisconnectAsync>d__3::<>u__1
0x223b  ldarg.0
0x223c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WaitForDisconnectAsync>d__3::<>t__builder
0x2241  ldloca.s 2
0x2243  ldarg.0
0x2244  call     T0x2B00001D
0x2249  leave.s  loc_229A
0x224b  ldarg.0
0x224c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <WaitForDisconnectAsync>d__3::<>u__1
0x2251  stloc.2
0x2252  ldarg.0
0x2253  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <WaitForDisconnectAsync>d__3::<>u__1
0x2258  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x225e  ldarg.0
0x225f  ldc.i4.m1
0x2260  dup
0x2261  stloc.0
0x2262  stfld    int32 <WaitForDisconnectAsync>d__3::<>1__state
0x2267  ldloca.s 2
0x2269  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x226e  leave.s  loc_2287
0x2270  stloc.3
0x2271  ldarg.0
0x2272  ldc.i4.s 0xFE
0x2274  stfld    int32 <WaitForDisconnectAsync>d__3::<>1__state
0x2279  ldarg.0
0x227a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WaitForDisconnectAsync>d__3::<>t__builder
0x227f  ldloc.3
0x2280  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x2285  leave.s  loc_229A
0x2287  ldarg.0
0x2288  ldc.i4.s 0xFE
0x228a  stfld    int32 <WaitForDisconnectAsync>d__3::<>1__state
0x228f  ldarg.0
0x2290  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WaitForDisconnectAsync>d__3::<>t__builder
0x2295  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x229a  ret
```
