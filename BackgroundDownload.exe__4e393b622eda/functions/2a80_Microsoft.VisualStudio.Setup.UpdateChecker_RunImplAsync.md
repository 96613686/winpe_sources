# Microsoft.VisualStudio.Setup.UpdateChecker::RunImplAsync

- ea: `0x2a80`
- end: `0x2abf`
- name: `Microsoft.VisualStudio.Setup.UpdateChecker::RunImplAsync`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2a80  ldloca.s 0
0x2a82  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::Create()
0x2a87  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <RunImplAsync>d__2::<>t__builder
0x2a8c  ldloca.s 0
0x2a8e  ldarg.0
0x2a8f  stfld    class Microsoft.VisualStudio.Setup.UpdateChecker <RunImplAsync>d__2::<>4__this
0x2a94  ldloca.s 0
0x2a96  ldarg.1
0x2a97  stfld    valuetype [mscorlib]System.Threading.CancellationToken <RunImplAsync>d__2::cancellationToken
0x2a9c  ldloca.s 0
0x2a9e  ldc.i4.m1
0x2a9f  stfld    int32 <RunImplAsync>d__2::<>1__state
0x2aa4  ldloca.s 0
0x2aa6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <RunImplAsync>d__2::<>t__builder
0x2aab  ldloca.s 0
0x2aad  call     T0x2B000039
0x2ab2  ldloca.s 0
0x2ab4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <RunImplAsync>d__2::<>t__builder
0x2ab9  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::get_Task()
0x2abe  ret
```
