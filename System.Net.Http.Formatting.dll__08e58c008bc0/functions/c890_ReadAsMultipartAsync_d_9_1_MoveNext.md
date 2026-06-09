# <ReadAsMultipartAsync>d__9`1::MoveNext

- ea: `0xc890`
- end: `0xcae1`
- name: `<ReadAsMultipartAsync>d__9`1::MoveNext`
- size: `593`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0xaf0`
- `0xb20`
- `0x1e40`
- `0x3890`
- `0xa7b0`
- `0xb3c0`
- `0xb410`
- `0xc7d0`
- `0xc890`

## pseudocode

```c

```

## disassembly

```asm
0xc890  ldarg.0
0xc891  ldfld    int32 valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>1__state
0xc896  stloc.0
0xc897  ldloc.0
0xc898  brfalse.s loc_C8FB
0xc89a  ldloc.0
0xc89b  ldc.i4.1
0xc89c  sub
0xc89d  ldc.i4.1
0xc89e  ble.un   loc_C98D
0xc8a3  ldarg.0
0xc8a4  ldfld    class [System.Net.Http]System.Net.Http.HttpContent valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::content
0xc8a9  brtrue.s loc_C8B6
0xc8ab  ldstr    aContent// "content"
0xc8b0  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0xc8b5  throw
0xc8b6  ldarg.0
0xc8b7  ldfld    var<u1> valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::streamProvider
0xc8bc  box      var<u1>
0xc8c1  brtrue.s loc_C8CE
0xc8c3  ldstr    aStreamprovider// "streamProvider"
0xc8c8  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0xc8cd  throw
0xc8ce  ldarg.0
0xc8cf  ldfld    int32 valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::bufferSize
0xc8d4  ldc.i4   0x100
0xc8d9  bge.s    loc_C8FB
0xc8db  ldstr    aBuffersize// "bufferSize"
0xc8e0  ldarg.0
0xc8e1  ldfld    int32 valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::bufferSize
0xc8e6  box      [mscorlib]System.Int32
0xc8eb  ldc.i4   0x100
0xc8f0  box      [mscorlib]System.Int32
0xc8f5  call     class [mscorlib]System.ArgumentOutOfRangeException System.Web.Http.Error::ArgumentMustBeGreaterThanOrEqualTo(string parameterName, object actualValue, object minValue)
0xc8fa  throw
0xc8fb  nop
0xc8fc  ldloc.0
0xc8fd  brfalse.s loc_C93C
0xc8ff  ldarg.0
0xc900  ldfld    class [System.Net.Http]System.Net.Http.HttpContent valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::content
0xc905  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.IO.Stream> [System.Net.Http]System.Net.Http.HttpContent::ReadAsStreamAsync()
0xc90a  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.IO.Stream>::GetAwaiter()
0xc90f  stloc.3
0xc910  ldloca.s 3
0xc912  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>::get_IsCompleted()
0xc917  brtrue.s loc_C958
0xc919  ldarg.0
0xc91a  ldc.i4.0
0xc91b  dup
0xc91c  stloc.0
0xc91d  stfld    int32 valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>1__state
0xc922  ldarg.0
0xc923  ldloc.3
0xc924  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>u__1
0xc929  ldarg.0
0xc92a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>t__builder
0xc92f  ldloca.s 3
0xc931  ldarg.0
0xc932  call     T0x2B000070
0xc937  leave    loc_CAE0
0xc93c  ldarg.0
0xc93d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>u__1
0xc942  stloc.3
0xc943  ldarg.0
0xc944  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream> valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>u__1
0xc949  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>
0xc94f  ldarg.0
0xc950  ldc.i4.m1
0xc951  dup
0xc952  stloc.0
0xc953  stfld    int32 valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>1__state
0xc958  ldloca.s 3
0xc95a  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.Stream>::GetResult()
0xc95f  stloc.2
0xc960  leave.s  loc_C971
0xc962  stloc.s  4
0xc964  call     string System.Net.Http.Properties.Resources::get_ReadAsMimeMultipartErrorReading()
0xc969  ldloc.s  4
0xc96b  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string, class [mscorlib]System.Exception)
0xc970  throw
0xc971  ldarg.0
0xc972  ldarg.0
0xc973  ldfld    class [System.Net.Http]System.Net.Http.HttpContent valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::content
0xc978  ldarg.0
0xc979  ldfld    var<u1> valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::streamProvider
0xc97e  box      var<u1>
0xc983  newobj   instance void System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser::.ctor(class [System.Net.Http]System.Net.Http.HttpContent content, class System.Net.Http.MultipartStreamProvider streamProvider)
0xc988  stfld    class System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<parser>5__2
0xc98d  nop
0xc98e  ldloc.0
0xc98f  ldc.i4.1
0xc990  beq.s    loc_CA03
0xc992  ldloc.0
0xc993  ldc.i4.2
0xc994  beq      loc_CA6E
0xc999  ldarg.0
0xc99a  ldfld    int32 valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::bufferSize
0xc99f  newarr   [mscorlib]System.Byte
0xc9a4  stloc.s  5
0xc9a6  ldloc.2
0xc9a7  ldarg.0
0xc9a8  ldfld    class System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<parser>5__2
0xc9ad  ldloc.s  5
0xc9af  ldarg.0
0xc9b0  ldfld    var<u1> valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::streamProvider
0xc9b5  box      var<u1>
0xc9ba  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.HttpContent> System.Net.Http.MultipartStreamProvider::get_Contents()
0xc9bf  newobj   instance void MultipartAsyncContext::.ctor(class [mscorlib]System.IO.Stream contentStream, class System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser mimeParser, unsigned int8[] data, class [mscorlib]System.Collections.Generic.ICollection`1<class [System.Net.Http]System.Net.Http.HttpContent> result)
0xc9c4  ldarg.0
0xc9c5  ldfld    valuetype [mscorlib]System.Threading.CancellationToken valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::cancellationToken
0xc9ca  call     class [mscorlib]System.Threading.Tasks.Task System.Net.Http.HttpContentMultipartExtensions::MultipartReadAsync(class MultipartAsyncContext context, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0xc9cf  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0xc9d4  stloc.s  6
0xc9d6  ldloca.s 6
0xc9d8  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0xc9dd  brtrue.s loc_CA20
0xc9df  ldarg.0
0xc9e0  ldc.i4.1
0xc9e1  dup
0xc9e2  stloc.0
0xc9e3  stfld    int32 valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>1__state
0xc9e8  ldarg.0
0xc9e9  ldloc.s  6
0xc9eb  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>u__2
0xc9f0  ldarg.0
0xc9f1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>t__builder
0xc9f6  ldloca.s 6
0xc9f8  ldarg.0
0xc9f9  call     T0x2B000071
0xc9fe  leave    loc_CAE0
0xca03  ldarg.0
0xca04  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>u__2
0xca09  stloc.s  6
0xca0b  ldarg.0
0xca0c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>u__2
0xca11  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0xca17  ldarg.0
0xca18  ldc.i4.m1
0xca19  dup
0xca1a  stloc.0
0xca1b  stfld    int32 valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>1__state
0xca20  ldloca.s 6
0xca22  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0xca27  ldarg.0
0xca28  ldfld    var<u1> valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::streamProvider
0xca2d  box      var<u1>
0xca32  ldarg.0
0xca33  ldfld    valuetype [mscorlib]System.Threading.CancellationToken valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::cancellationToken
0xca38  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Net.Http.MultipartStreamProvider::ExecutePostProcessingAsync(valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0xca3d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0xca42  stloc.s  6
0xca44  ldloca.s 6
0xca46  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0xca4b  brtrue.s loc_CA8B
0xca4d  ldarg.0
0xca4e  ldc.i4.2
0xca4f  dup
0xca50  stloc.0
0xca51  stfld    int32 valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>1__state
0xca56  ldarg.0
0xca57  ldloc.s  6
0xca59  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>u__2
0xca5e  ldarg.0
0xca5f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>t__builder
0xca64  ldloca.s 6
0xca66  ldarg.0
0xca67  call     T0x2B000071
0xca6c  leave.s  loc_CAE0
0xca6e  ldarg.0
0xca6f  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>u__2
0xca74  stloc.s  6
0xca76  ldarg.0
0xca77  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>u__2
0xca7c  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0xca82  ldarg.0
0xca83  ldc.i4.m1
0xca84  dup
0xca85  stloc.0
0xca86  stfld    int32 valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>1__state
0xca8b  ldloca.s 6
0xca8d  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0xca92  ldarg.0
0xca93  ldfld    var<u1> valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::streamProvider
0xca98  stloc.1
0xca99  leave.s  loc_CACC
0xca9b  ldloc.0
0xca9c  ldc.i4.0
0xca9d  bge.s    loc_CAB2
0xca9f  ldarg.0
0xcaa0  ldfld    class System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<parser>5__2
0xcaa5  brfalse.s loc_CAB2
0xcaa7  ldarg.0
0xcaa8  ldfld    class System.Net.Http.Formatting.Parsers.MimeMultipartBodyPartParser valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<parser>5__2
0xcaad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcab2  endfinally
0xcab3  stloc.s  7
0xcab5  ldarg.0
0xcab6  ldc.i4.s 0xFE
0xcab8  stfld    int32 valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>1__state
0xcabd  ldarg.0
0xcabe  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>t__builder
0xcac3  ldloc.s  7
0xcac5  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetException(class [mscorlib]System.Exception)
0xcaca  leave.s  loc_CAE0
0xcacc  ldarg.0
0xcacd  ldc.i4.s 0xFE
0xcacf  stfld    int32 valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>1__state
0xcad4  ldarg.0
0xcad5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <ReadAsMultipartAsync>d__9`1<var<u1>>::<>t__builder
0xcada  ldloc.1
0xcadb  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetResult(var<u1>)
0xcae0  ret
```
