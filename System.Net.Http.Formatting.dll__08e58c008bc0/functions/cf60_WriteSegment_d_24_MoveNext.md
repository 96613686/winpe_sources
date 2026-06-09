# <WriteSegment>d__24::MoveNext

- ea: `0xcf60`
- end: `0xd022`
- name: `<WriteSegment>d__24::MoveNext`
- size: `194`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x2910`
- `0xcf60`

## pseudocode

```c

```

## disassembly

```asm
0xcf60  ldarg.0
0xcf61  ldfld    int32 <WriteSegment>d__24::<>1__state
0xcf66  stloc.0
0xcf67  ldarg.0
0xcf68  ldfld    class System.Net.Http.MimeBodyPart <WriteSegment>d__24::<>4__this
0xcf6d  stloc.1
0xcf6e  ldloc.0
0xcf6f  brfalse.s loc_CFD2
0xcf71  ldloc.1
0xcf72  call     instance class [mscorlib]System.IO.Stream System.Net.Http.MimeBodyPart::GetOutputStream()
0xcf77  ldarg.0
0xcf78  ldflda   valuetype [mscorlib]System.ArraySegment`1<unsigned int8> <WriteSegment>d__24::segment
0xcf7d  call     instance var<u1>[] valuetype [mscorlib]System.ArraySegment`1<unsigned int8>::get_Array()
0xcf82  ldarg.0
0xcf83  ldflda   valuetype [mscorlib]System.ArraySegment`1<unsigned int8> <WriteSegment>d__24::segment
0xcf88  call     instance int32 valuetype [mscorlib]System.ArraySegment`1<unsigned int8>::get_Offset()
0xcf8d  ldarg.0
0xcf8e  ldflda   valuetype [mscorlib]System.ArraySegment`1<unsigned int8> <WriteSegment>d__24::segment
0xcf93  call     instance int32 valuetype [mscorlib]System.ArraySegment`1<unsigned int8>::get_Count()
0xcf98  ldarg.0
0xcf99  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <WriteSegment>d__24::cancellationToken
0xcf9e  callvirt instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.IO.Stream::WriteAsync(unsigned int8[], int32, int32, valuetype [mscorlib]System.Threading.CancellationToken)
0xcfa3  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0xcfa8  stloc.2
0xcfa9  ldloca.s 2
0xcfab  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0xcfb0  brtrue.s loc_CFEE
0xcfb2  ldarg.0
0xcfb3  ldc.i4.0
0xcfb4  dup
0xcfb5  stloc.0
0xcfb6  stfld    int32 <WriteSegment>d__24::<>1__state
0xcfbb  ldarg.0
0xcfbc  ldloc.2
0xcfbd  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <WriteSegment>d__24::<>u__1
0xcfc2  ldarg.0
0xcfc3  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteSegment>d__24::<>t__builder
0xcfc8  ldloca.s 2
0xcfca  ldarg.0
0xcfcb  call     T0x2B000076
0xcfd0  leave.s  loc_D021
0xcfd2  ldarg.0
0xcfd3  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <WriteSegment>d__24::<>u__1
0xcfd8  stloc.2
0xcfd9  ldarg.0
0xcfda  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <WriteSegment>d__24::<>u__1
0xcfdf  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0xcfe5  ldarg.0
0xcfe6  ldc.i4.m1
0xcfe7  dup
0xcfe8  stloc.0
0xcfe9  stfld    int32 <WriteSegment>d__24::<>1__state
0xcfee  ldloca.s 2
0xcff0  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0xcff5  leave.s  loc_D00E
0xcff7  stloc.3
0xcff8  ldarg.0
0xcff9  ldc.i4.s 0xFE
0xcffb  stfld    int32 <WriteSegment>d__24::<>1__state
0xd000  ldarg.0
0xd001  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteSegment>d__24::<>t__builder
0xd006  ldloc.3
0xd007  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0xd00c  leave.s  loc_D021
0xd00e  ldarg.0
0xd00f  ldc.i4.s 0xFE
0xd011  stfld    int32 <WriteSegment>d__24::<>1__state
0xd016  ldarg.0
0xd017  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteSegment>d__24::<>t__builder
0xd01c  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0xd021  ret
```
