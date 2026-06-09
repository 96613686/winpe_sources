# Microsoft.BIServer.Management.WebHost.RequestLoggingMiddleWare::Invoke

- ea: `0x220`
- end: `0x261`
- name: `Microsoft.BIServer.Management.WebHost.RequestLoggingMiddleWare::Invoke`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x220  ldloca.s 0
0x222  ldarg.0
0x223  stfld    class Microsoft.BIServer.Management.WebHost.RequestLoggingMiddleWare <Invoke>d__2::<>4__this
0x228  ldloca.s 0
0x22a  ldarg.1
0x22b  stfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x230  ldloca.s 0
0x232  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::Create()
0x237  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__2::<>t__builder
0x23c  ldloca.s 0
0x23e  ldc.i4.m1
0x23f  stfld    int32 <Invoke>d__2::<>1__state
0x244  ldloc.0
0x245  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__2::<>t__builder
0x24a  stloc.1
0x24b  ldloca.s 1
0x24d  ldloca.s 0
0x24f  call     T0x2B000003
0x254  ldloca.s 0
0x256  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__2::<>t__builder
0x25b  call     instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::get_Task()
0x260  ret
```
