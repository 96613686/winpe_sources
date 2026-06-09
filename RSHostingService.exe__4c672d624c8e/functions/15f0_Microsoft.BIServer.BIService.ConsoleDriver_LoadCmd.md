# Microsoft.BIServer.BIService.ConsoleDriver::LoadCmd

- ea: `0x15f0`
- end: `0x161d`
- name: `Microsoft.BIServer.BIService.ConsoleDriver::LoadCmd`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1520`

## pseudocode

```c

```

## disassembly

```asm
0x15f0  ldloca.s 0
0x15f2  ldarg.0
0x15f3  stfld    class Microsoft.BIServer.BIService.ConsoleDriver <LoadCmd>d__4::<>4__this
0x15f8  ldloca.s 0
0x15fa  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder::Create()
0x15ff  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <LoadCmd>d__4::<>t__builder
0x1604  ldloca.s 0
0x1606  ldc.i4.m1
0x1607  stfld    int32 <LoadCmd>d__4::<>1__state
0x160c  ldloc.0
0x160d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <LoadCmd>d__4::<>t__builder
0x1612  stloc.1
0x1613  ldloca.s 1
0x1615  ldloca.s 0
0x1617  call     T0x2B000014
0x161c  ret
```
