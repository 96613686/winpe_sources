# Microsoft.BIServer.BIService.ManagedProcess::ThrottledStart

- ea: `0x1ee0`
- end: `0x1f0d`
- name: `Microsoft.BIServer.BIService.ManagedProcess::ThrottledStart`
- size: `45`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18a0`
- `0x19f0`
- `0x2000`

## pseudocode

```c

```

## disassembly

```asm
0x1ee0  ldloca.s 0
0x1ee2  ldarg.0
0x1ee3  stfld    class Microsoft.BIServer.BIService.ManagedProcess <ThrottledStart>d__20::<>4__this
0x1ee8  ldloca.s 0
0x1eea  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder::Create()
0x1eef  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <ThrottledStart>d__20::<>t__builder
0x1ef4  ldloca.s 0
0x1ef6  ldc.i4.m1
0x1ef7  stfld    int32 <ThrottledStart>d__20::<>1__state
0x1efc  ldloc.0
0x1efd  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <ThrottledStart>d__20::<>t__builder
0x1f02  stloc.1
0x1f03  ldloca.s 1
0x1f05  ldloca.s 0
0x1f07  call     T0x2B000016
0x1f0c  ret
```
