# <SerializeToStreamAsync>d__29::MoveNext

- ea: `0xcd90`
- end: `0xcf39`
- name: `<SerializeToStreamAsync>d__29::MoveNext`
- size: `425`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1ff0`
- `0x24c0`
- `0x2560`
- `0xb3c0`
- `0xcd90`

## pseudocode

```c

```

## disassembly

```asm
0xcd90  ldarg.0
0xcd91  ldfld    int32 <SerializeToStreamAsync>d__29::<>1__state
0xcd96  stloc.0
0xcd97  ldarg.0
0xcd98  ldfld    class System.Net.Http.HttpMessageContent <SerializeToStreamAsync>d__29::<>4__this
0xcd9d  stloc.1
0xcd9e  ldloc.0
0xcd9f  switch   loc_CE0C, loc_CE79, loc_CEE7
0xcdb0  ldarg.0
0xcdb1  ldfld    class [mscorlib]System.IO.Stream <SerializeToStreamAsync>d__29::stream
0xcdb6  brtrue.s loc_CDC3
0xcdb8  ldstr    aStream// "stream"
0xcdbd  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0xcdc2  throw
0xcdc3  ldloc.1
0xcdc4  call     instance unsigned int8[] System.Net.Http.HttpMessageContent::SerializeHeader()
0xcdc9  stloc.2
0xcdca  ldarg.0
0xcdcb  ldfld    class [mscorlib]System.IO.Stream <SerializeToStreamAsync>d__29::stream
0xcdd0  ldloc.2
0xcdd1  ldc.i4.0
0xcdd2  ldloc.2
0xcdd3  ldlen
0xcdd4  conv.i4
0xcdd5  callvirt instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.IO.Stream::WriteAsync(unsigned int8[], int32, int32)
0xcdda  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0xcddf  stloc.3
0xcde0  ldloca.s 3
0xcde2  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0xcde7  brtrue.s loc_CE28
0xcde9  ldarg.0
0xcdea  ldc.i4.0
0xcdeb  dup
0xcdec  stloc.0
0xcded  stfld    int32 <SerializeToStreamAsync>d__29::<>1__state
0xcdf2  ldarg.0
0xcdf3  ldloc.3
0xcdf4  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SerializeToStreamAsync>d__29::<>u__1
0xcdf9  ldarg.0
0xcdfa  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SerializeToStreamAsync>d__29::<>t__builder
0xcdff  ldloca.s 3
0xce01  ldarg.0
0xce02  call     T0x2B000074
0xce07  leave    loc_CF38
0xce0c  ldarg.0
0xce0d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SerializeToStreamAsync>d__29::<>u__1
0xce12  stloc.3
0xce13  ldarg.0
0xce14  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SerializeToStreamAsync>d__29::<>u__1
0xce19  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0xce1f  ldarg.0
0xce20  ldc.i4.m1
0xce21  dup
0xce22  stloc.0
0xce23  stfld    int32 <SerializeToStreamAsync>d__29::<>1__state
0xce28  ldloca.s 3
0xce2a  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0xce2f  ldloc.1
0xce30  call     instance class [System.Net.Http]System.Net.Http.HttpContent System.Net.Http.HttpMessageContent::get_Content()
0xce35  brfalse  loc_CF0A
0xce3a  ldloc.1
0xce3b  ldfld    class [mscorlib]System.Lazy`1<class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.IO.Stream>> System.Net.Http.HttpMessageContent::_streamTask
0xce40  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.IO.Stream>>::get_Value()
0xce45  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.IO.Stream>::GetAwaiter()
0xce4a  stloc.s  5
0xce4c  ldloca.s 5
0xce4e  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>::get_IsCompleted()
0xce53  brtrue.s loc_CE96
0xce55  ldarg.0
0xce56  ldc.i4.1
0xce57  dup
0xce58  stloc.0
0xce59  stfld    int32 <SerializeToStreamAsync>d__29::<>1__state
0xce5e  ldarg.0
0xce5f  ldloc.s  5
0xce61  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> <SerializeToStreamAsync>d__29::<>u__2
0xce66  ldarg.0
0xce67  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SerializeToStreamAsync>d__29::<>t__builder
0xce6c  ldloca.s 5
0xce6e  ldarg.0
0xce6f  call     T0x2B000075
0xce74  leave    loc_CF38
0xce79  ldarg.0
0xce7a  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> <SerializeToStreamAsync>d__29::<>u__2
0xce7f  stloc.s  5
0xce81  ldarg.0
0xce82  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> <SerializeToStreamAsync>d__29::<>u__2
0xce87  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>
0xce8d  ldarg.0
0xce8e  ldc.i4.m1
0xce8f  dup
0xce90  stloc.0
0xce91  stfld    int32 <SerializeToStreamAsync>d__29::<>1__state
0xce96  ldloca.s 5
0xce98  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>::GetResult()
0xce9d  stloc.s  4
0xce9f  ldloc.1
0xcea0  ldloc.s  4
0xcea2  call     instance void System.Net.Http.HttpMessageContent::ValidateStreamForReading(class [mscorlib]System.IO.Stream stream)
0xcea7  ldloc.1
0xcea8  call     instance class [System.Net.Http]System.Net.Http.HttpContent System.Net.Http.HttpMessageContent::get_Content()
0xcead  ldarg.0
0xceae  ldfld    class [mscorlib]System.IO.Stream <SerializeToStreamAsync>d__29::stream
0xceb3  callvirt instance class [mscorlib]System.Threading.Tasks.Task [System.Net.Http]System.Net.Http.HttpContent::CopyToAsync(class [mscorlib]System.IO.Stream)
0xceb8  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0xcebd  stloc.3
0xcebe  ldloca.s 3
0xcec0  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0xcec5  brtrue.s loc_CF03
0xcec7  ldarg.0
0xcec8  ldc.i4.2
0xcec9  dup
0xceca  stloc.0
0xcecb  stfld    int32 <SerializeToStreamAsync>d__29::<>1__state
0xced0  ldarg.0
0xced1  ldloc.3
0xced2  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SerializeToStreamAsync>d__29::<>u__1
0xced7  ldarg.0
0xced8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SerializeToStreamAsync>d__29::<>t__builder
0xcedd  ldloca.s 3
0xcedf  ldarg.0
0xcee0  call     T0x2B000074
0xcee5  leave.s  loc_CF38
0xcee7  ldarg.0
0xcee8  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SerializeToStreamAsync>d__29::<>u__1
0xceed  stloc.3
0xceee  ldarg.0
0xceef  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <SerializeToStreamAsync>d__29::<>u__1
0xcef4  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0xcefa  ldarg.0
0xcefb  ldc.i4.m1
0xcefc  dup
0xcefd  stloc.0
0xcefe  stfld    int32 <SerializeToStreamAsync>d__29::<>1__state
0xcf03  ldloca.s 3
0xcf05  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0xcf0a  leave.s  loc_CF25
0xcf0c  stloc.s  6
0xcf0e  ldarg.0
0xcf0f  ldc.i4.s 0xFE
0xcf11  stfld    int32 <SerializeToStreamAsync>d__29::<>1__state
0xcf16  ldarg.0
0xcf17  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SerializeToStreamAsync>d__29::<>t__builder
0xcf1c  ldloc.s  6
0xcf1e  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0xcf23  leave.s  loc_CF38
0xcf25  ldarg.0
0xcf26  ldc.i4.s 0xFE
0xcf28  stfld    int32 <SerializeToStreamAsync>d__29::<>1__state
0xcf2d  ldarg.0
0xcf2e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SerializeToStreamAsync>d__29::<>t__builder
0xcf33  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0xcf38  ret
```
