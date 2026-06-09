# <ReadAsAsyncCore>d__4::MoveNext

- ea: `0xbcd0`
- end: `0xbd81`
- name: `<ReadAsAsyncCore>d__4::MoveNext`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x5fd0`
- `0xbcd0`

## pseudocode

```c

```

## disassembly

```asm
0xbcd0  ldarg.0
0xbcd1  ldfld    int32 <ReadAsAsyncCore>d__4::<>1__state
0xbcd6  stloc.0
0xbcd7  ldloc.0
0xbcd8  brfalse.s loc_BD20
0xbcda  ldarg.0
0xbcdb  ldfld    class [System.Net.Http]System.Net.Http.HttpContent <ReadAsAsyncCore>d__4::content
0xbce0  ldarg.0
0xbce1  ldfld    class System.Net.Http.Formatting.MediaTypeFormatter[] <ReadAsAsyncCore>d__4::formatters
0xbce6  ldarg.0
0xbce7  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ReadAsAsyncCore>d__4::cancellationToken
0xbcec  call     T0x2B000064
0xbcf1  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class System.Net.Http.Formatting.FormDataCollection>::GetAwaiter()
0xbcf6  stloc.3
0xbcf7  ldloca.s 3
0xbcf9  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class System.Net.Http.Formatting.FormDataCollection>::get_IsCompleted()
0xbcfe  brtrue.s loc_BD3C
0xbd00  ldarg.0
0xbd01  ldc.i4.0
0xbd02  dup
0xbd03  stloc.0
0xbd04  stfld    int32 <ReadAsAsyncCore>d__4::<>1__state
0xbd09  ldarg.0
0xbd0a  ldloc.3
0xbd0b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class System.Net.Http.Formatting.FormDataCollection> <ReadAsAsyncCore>d__4::<>u__1
0xbd10  ldarg.0
0xbd11  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System]System.Collections.Specialized.NameValueCollection> <ReadAsAsyncCore>d__4::<>t__builder
0xbd16  ldloca.s 3
0xbd18  ldarg.0
0xbd19  call     T0x2B000065
0xbd1e  leave.s  loc_BD80
0xbd20  ldarg.0
0xbd21  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class System.Net.Http.Formatting.FormDataCollection> <ReadAsAsyncCore>d__4::<>u__1
0xbd26  stloc.3
0xbd27  ldarg.0
0xbd28  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class System.Net.Http.Formatting.FormDataCollection> <ReadAsAsyncCore>d__4::<>u__1
0xbd2d  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class System.Net.Http.Formatting.FormDataCollection>
0xbd33  ldarg.0
0xbd34  ldc.i4.m1
0xbd35  dup
0xbd36  stloc.0
0xbd37  stfld    int32 <ReadAsAsyncCore>d__4::<>1__state
0xbd3c  ldloca.s 3
0xbd3e  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class System.Net.Http.Formatting.FormDataCollection>::GetResult()
0xbd43  stloc.2
0xbd44  ldloc.2
0xbd45  brfalse.s loc_BD4F
0xbd47  ldloc.2
0xbd48  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Net.Http.Formatting.FormDataCollection::ReadAsNameValueCollection()
0xbd4d  br.s     loc_BD50
0xbd4f  ldnull
0xbd50  stloc.1
0xbd51  leave.s  loc_BD6C
0xbd53  stloc.s  4
0xbd55  ldarg.0
0xbd56  ldc.i4.s 0xFE
0xbd58  stfld    int32 <ReadAsAsyncCore>d__4::<>1__state
0xbd5d  ldarg.0
0xbd5e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System]System.Collections.Specialized.NameValueCollection> <ReadAsAsyncCore>d__4::<>t__builder
0xbd63  ldloc.s  4
0xbd65  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System]System.Collections.Specialized.NameValueCollection>::SetException(class [mscorlib]System.Exception)
0xbd6a  leave.s  loc_BD80
0xbd6c  ldarg.0
0xbd6d  ldc.i4.s 0xFE
0xbd6f  stfld    int32 <ReadAsAsyncCore>d__4::<>1__state
0xbd74  ldarg.0
0xbd75  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System]System.Collections.Specialized.NameValueCollection> <ReadAsAsyncCore>d__4::<>t__builder
0xbd7a  ldloc.1
0xbd7b  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System]System.Collections.Specialized.NameValueCollection>::SetResult(var<u1>)
0xbd80  ret
```
