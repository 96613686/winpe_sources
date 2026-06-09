# <MultipartReadAsync>d__10::MoveNext

- ea: `0xcb10`
- end: `0xcd70`
- name: `<MultipartReadAsync>d__10::MoveNext`
- size: `608`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x1e90`
- `0x2860`
- `0x28c0`
- `0x29f0`
- `0x3890`
- `0x38b0`
- `0xa860`
- `0xc800`
- `0xc820`
- `0xc840`
- `0xc860`
- `0xcb10`

## pseudocode

```c

```

## disassembly

```asm
0xcb10  ldarg.0
0xcb11  ldfld    int32 <MultipartReadAsync>d__10::<>1__state
0xcb16  stloc.0
0xcb17  ldloc.0
0xcb18  brfalse.s loc_CB21
0xcb1a  ldloc.0
0xcb1b  ldc.i4.1
0xcb1c  beq      loc_CBE4
0xcb21  nop
0xcb22  ldloc.0
0xcb23  brfalse.s loc_CB86
0xcb25  ldarg.0
0xcb26  ldfld    class MultipartAsyncContext <MultipartReadAsync>d__10::context
0xcb2b  callvirt instance class [mscorlib]System.IO.Stream MultipartAsyncContext::get_ContentStream()
0xcb30  ldarg.0
0xcb31  ldfld    class MultipartAsyncContext <MultipartReadAsync>d__10::context
0xcb36  callvirt instance unsigned int8[] MultipartAsyncContext::get_Data()
0xcb3b  ldc.i4.0
0xcb3c  ldarg.0
0xcb3d  ldfld    class MultipartAsyncContext <MultipartReadAsync>d__10::context
0xcb42  callvirt instance unsigned int8[] MultipartAsyncContext::get_Data()
0xcb47  ldlen
0xcb48  conv.i4
0xcb49  ldarg.0
0xcb4a  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <MultipartReadAsync>d__10::cancellationToken
0xcb4f  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [mscorlib]System.IO.Stream::ReadAsync(unsigned int8[], int32, int32, valuetype [mscorlib]System.Threading.CancellationToken)
0xcb54  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0xcb59  stloc.3
0xcb5a  ldloca.s 3
0xcb5c  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0xcb61  brtrue.s loc_CBA2
0xcb63  ldarg.0
0xcb64  ldc.i4.0
0xcb65  dup
0xcb66  stloc.0
0xcb67  stfld    int32 <MultipartReadAsync>d__10::<>1__state
0xcb6c  ldarg.0
0xcb6d  ldloc.3
0xcb6e  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <MultipartReadAsync>d__10::<>u__1
0xcb73  ldarg.0
0xcb74  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <MultipartReadAsync>d__10::<>t__builder
0xcb79  ldloca.s 3
0xcb7b  ldarg.0
0xcb7c  call     T0x2B000072
0xcb81  leave    loc_CD6F
0xcb86  ldarg.0
0xcb87  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <MultipartReadAsync>d__10::<>u__1
0xcb8c  stloc.3
0xcb8d  ldarg.0
0xcb8e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <MultipartReadAsync>d__10::<>u__1
0xcb93  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>
0xcb99  ldarg.0
0xcb9a  ldc.i4.m1
0xcb9b  dup
0xcb9c  stloc.0
0xcb9d  stfld    int32 <MultipartReadAsync>d__10::<>1__state
0xcba2  ldloca.s 3
0xcba4  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::GetResult()
0xcba9  stloc.1
0xcbaa  leave.s  loc_CBBB
0xcbac  stloc.s  4
0xcbae  call     string System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartErrorReading()
0xcbb3  ldloc.s  4
0xcbb5  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string, class [mscorlib]System.Exception)
0xcbba  throw
0xcbbb  ldarg.0
0xcbbc  ldfld    class MultipartAsyncContext <MultipartReadAsync>d__10::context
0xcbc1  callvirt instance class System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser MultipartAsyncContext::get_MimeParser()
0xcbc6  ldarg.0
0xcbc7  ldfld    class MultipartAsyncContext <MultipartReadAsync>d__10::context
0xcbcc  callvirt instance unsigned int8[] MultipartAsyncContext::get_Data()
0xcbd1  ldloc.1
0xcbd2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Net.Http.MimeBodyPart> System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::ParseBuffer(unsigned int8[] data, int32 bytesRead)
0xcbd7  stloc.2
0xcbd8  ldarg.0
0xcbd9  ldloc.2
0xcbda  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Net.Http.MimeBodyPart>::GetEnumerator()
0xcbdf  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Net.Http.MimeBodyPart> <MultipartReadAsync>d__10::<>7__wrap1
0xcbe4  nop
0xcbe5  ldloc.0
0xcbe6  ldc.i4.1
0xcbe7  beq.s    loc_CC15
0xcbe9  br       loc_CD0D
0xcbee  ldarg.0
0xcbef  ldarg.0
0xcbf0  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Net.Http.MimeBodyPart> <MultipartReadAsync>d__10::<>7__wrap1
0xcbf5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Net.Http.MimeBodyPart>::get_Current()
0xcbfa  stfld    class System.Net.Http.MimeBodyPart <MultipartReadAsync>d__10::<part>5__3
0xcbff  ldarg.0
0xcc00  ldarg.0
0xcc01  ldfld    class System.Net.Http.MimeBodyPart <MultipartReadAsync>d__10::<part>5__3
0xcc06  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.ArraySegment`1<unsigned int8>> System.Net.Http.MimeBodyPart::get_Segments()
0xcc0b  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.ArraySegment`1<unsigned int8>>::GetEnumerator()
0xcc10  stfld    valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.ArraySegment`1<unsigned int8>> <MultipartReadAsync>d__10::<>7__wrap3
0xcc15  nop
0xcc16  ldloc.0
0xcc17  ldc.i4.1
0xcc18  beq.s    loc_CC2C
0xcc1a  br       loc_CCB8
0xcc1f  ldarg.0
0xcc20  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.ArraySegment`1<unsigned int8>> <MultipartReadAsync>d__10::<>7__wrap3
0xcc25  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.ArraySegment`1<unsigned int8>>::get_Current()
0xcc2a  stloc.s  5
0xcc2c  nop
0xcc2d  ldloc.0
0xcc2e  ldc.i4.1
0xcc2f  beq.s    loc_CC78
0xcc31  ldarg.0
0xcc32  ldfld    class System.Net.Http.MimeBodyPart <MultipartReadAsync>d__10::<part>5__3
0xcc37  ldloc.s  5
0xcc39  ldarg.0
0xcc3a  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <MultipartReadAsync>d__10::cancellationToken
0xcc3f  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Net.Http.MimeBodyPart::WriteSegment(valuetype [mscorlib]System.ArraySegment`1<unsigned int8> segment, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0xcc44  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0xcc49  stloc.s  6
0xcc4b  ldloca.s 6
0xcc4d  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0xcc52  brtrue.s loc_CC95
0xcc54  ldarg.0
0xcc55  ldc.i4.1
0xcc56  dup
0xcc57  stloc.0
0xcc58  stfld    int32 <MultipartReadAsync>d__10::<>1__state
0xcc5d  ldarg.0
0xcc5e  ldloc.s  6
0xcc60  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <MultipartReadAsync>d__10::<>u__2
0xcc65  ldarg.0
0xcc66  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <MultipartReadAsync>d__10::<>t__builder
0xcc6b  ldloca.s 6
0xcc6d  ldarg.0
0xcc6e  call     T0x2B000073
0xcc73  leave    loc_CD6F
0xcc78  ldarg.0
0xcc79  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <MultipartReadAsync>d__10::<>u__2
0xcc7e  stloc.s  6
0xcc80  ldarg.0
0xcc81  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <MultipartReadAsync>d__10::<>u__2
0xcc86  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0xcc8c  ldarg.0
0xcc8d  ldc.i4.m1
0xcc8e  dup
0xcc8f  stloc.0
0xcc90  stfld    int32 <MultipartReadAsync>d__10::<>1__state
0xcc95  ldloca.s 6
0xcc97  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0xcc9c  leave.s  loc_CCB8
0xcc9e  stloc.s  7
0xcca0  ldarg.0
0xcca1  ldfld    class System.Net.Http.MimeBodyPart <MultipartReadAsync>d__10::<part>5__3
0xcca6  callvirt instance void System.Net.Http.MimeBodyPart::Dispose()
0xccab  call     string System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartErrorWriting()
0xccb0  ldloc.s  7
0xccb2  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string, class [mscorlib]System.Exception)
0xccb7  throw
0xccb8  ldarg.0
0xccb9  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.ArraySegment`1<unsigned int8>> <MultipartReadAsync>d__10::<>7__wrap3
0xccbe  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.ArraySegment`1<unsigned int8>>::MoveNext()
0xccc3  brtrue   loc_CC1F
0xccc8  leave.s  loc_CCE0
0xccca  ldloc.0
0xcccb  ldc.i4.0
0xcccc  bge.s    loc_CCDF
0xccce  ldarg.0
0xcccf  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.ArraySegment`1<unsigned int8>> <MultipartReadAsync>d__10::<>7__wrap3
0xccd4  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.ArraySegment`1<unsigned int8>>
0xccda  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xccdf  endfinally
0xcce0  ldarg.0
0xcce1  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.ArraySegment`1<unsigned int8>> <MultipartReadAsync>d__10::<>7__wrap3
0xcce6  initobj  valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.ArraySegment`1<unsigned int8>>
0xccec  ldarg.0
0xcced  ldfld    class System.Net.Http.MimeBodyPart <MultipartReadAsync>d__10::<part>5__3
0xccf2  ldarg.0
0xccf3  ldfld    class MultipartAsyncContext <MultipartReadAsync>d__10::context
0xccf8  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [System.Net.Http]System.Net.Http.HttpContent> MultipartAsyncContext::get_Result()
0xccfd  call     bool System.Net.Http.HttpContentMultipartExtensions::CheckIsFinalPart(class System.Net.Http.MimeBodyPart part, class [mscorlib]System.Collections.Generic.ICollection`1<class [System.Net.Http]System.Net.Http.HttpContent> result)
0xcd02  brfalse.s loc_CD06
0xcd04  leave.s  loc_CD5C
0xcd06  ldarg.0
0xcd07  ldnull
0xcd08  stfld    class System.Net.Http.MimeBodyPart <MultipartReadAsync>d__10::<part>5__3
0xcd0d  ldarg.0
0xcd0e  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Net.Http.MimeBodyPart> <MultipartReadAsync>d__10::<>7__wrap1
0xcd13  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xcd18  brtrue   loc_CBEE
0xcd1d  leave.s  loc_CD37
0xcd1f  ldloc.0
0xcd20  ldc.i4.0
0xcd21  bge.s    loc_CD36
0xcd23  ldarg.0
0xcd24  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Net.Http.MimeBodyPart> <MultipartReadAsync>d__10::<>7__wrap1
0xcd29  brfalse.s loc_CD36
0xcd2b  ldarg.0
0xcd2c  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Net.Http.MimeBodyPart> <MultipartReadAsync>d__10::<>7__wrap1
0xcd31  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcd36  endfinally
0xcd37  ldarg.0
0xcd38  ldnull
0xcd39  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Net.Http.MimeBodyPart> <MultipartReadAsync>d__10::<>7__wrap1
0xcd3e  br       loc_CB21
0xcd43  stloc.s  8
0xcd45  ldarg.0
0xcd46  ldc.i4.s 0xFE
0xcd48  stfld    int32 <MultipartReadAsync>d__10::<>1__state
0xcd4d  ldarg.0
0xcd4e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <MultipartReadAsync>d__10::<>t__builder
0xcd53  ldloc.s  8
0xcd55  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0xcd5a  leave.s  loc_CD6F
0xcd5c  ldarg.0
0xcd5d  ldc.i4.s 0xFE
0xcd5f  stfld    int32 <MultipartReadAsync>d__10::<>1__state
0xcd64  ldarg.0
0xcd65  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <MultipartReadAsync>d__10::<>t__builder
0xcd6a  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0xcd6f  ret
```
