# <ReadFormDataAsync>d__1::MoveNext

- ea: `0xbdb0`
- end: `0xbefc`
- name: `<ReadFormDataAsync>d__1::MoveNext`
- size: `332`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1350`
- `0xbdb0`

## pseudocode

```c

```

## disassembly

```asm
0xbdb0  ldarg.0
0xbdb1  ldfld    int32 <ReadFormDataAsync>d__1::<>1__state
0xbdb6  stloc.0
0xbdb7  ldloc.0
0xbdb8  brfalse.s loc_BDCB
0xbdba  ldarg.0
0xbdbb  ldarg.0
0xbdbc  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.HttpContent> <ReadFormDataAsync>d__1::contents
0xbdc1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.HttpContent>::GetEnumerator()
0xbdc6  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Net.Http]System.Net.Http.HttpContent> <ReadFormDataAsync>d__1::<>7__wrap1
0xbdcb  nop
0xbdcc  ldloc.0
0xbdcd  brfalse  loc_BE5E
0xbdd2  br       loc_BE9C
0xbdd7  ldarg.0
0xbdd8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Net.Http]System.Net.Http.HttpContent> <ReadFormDataAsync>d__1::<>7__wrap1
0xbddd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Net.Http]System.Net.Http.HttpContent>::get_Current()
0xbde2  stloc.1
0xbde3  ldloc.1
0xbde4  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0xbde9  callvirt instance class [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentDisposition()
0xbdee  stloc.2
0xbdef  ldloc.2
0xbdf0  callvirt instance string [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue::get_FileName()
0xbdf5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbdfa  brfalse  loc_BE9C
0xbdff  ldarg.0
0xbe00  ldloc.2
0xbe01  callvirt instance string [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue::get_Name()
0xbe06  call     string System.Net.Http.FormattingUtilities::UnquoteToken(string token)
0xbe0b  dup
0xbe0c  brtrue.s loc_BE14
0xbe0e  pop
0xbe0f  ldsfld   string [mscorlib]System.String::Empty
0xbe14  stfld    string <ReadFormDataAsync>d__1::<formFieldName>5__3
0xbe19  ldarg.0
0xbe1a  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <ReadFormDataAsync>d__1::cancellationToken
0xbe1f  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0xbe24  ldloc.1
0xbe25  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> [System.Net.Http]System.Net.Http.HttpContent::ReadAsStringAsync()
0xbe2a  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0xbe2f  stloc.s  4
0xbe31  ldloca.s 4
0xbe33  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0xbe38  brtrue.s loc_BE7B
0xbe3a  ldarg.0
0xbe3b  ldc.i4.0
0xbe3c  dup
0xbe3d  stloc.0
0xbe3e  stfld    int32 <ReadFormDataAsync>d__1::<>1__state
0xbe43  ldarg.0
0xbe44  ldloc.s  4
0xbe46  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <ReadFormDataAsync>d__1::<>u__1
0xbe4b  ldarg.0
0xbe4c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ReadFormDataAsync>d__1::<>t__builder
0xbe51  ldloca.s 4
0xbe53  ldarg.0
0xbe54  call     T0x2B000066
0xbe59  leave    loc_BEFB
0xbe5e  ldarg.0
0xbe5f  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <ReadFormDataAsync>d__1::<>u__1
0xbe64  stloc.s  4
0xbe66  ldarg.0
0xbe67  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <ReadFormDataAsync>d__1::<>u__1
0xbe6c  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0xbe72  ldarg.0
0xbe73  ldc.i4.m1
0xbe74  dup
0xbe75  stloc.0
0xbe76  stfld    int32 <ReadFormDataAsync>d__1::<>1__state
0xbe7b  ldloca.s 4
0xbe7d  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0xbe82  stloc.3
0xbe83  ldarg.0
0xbe84  ldfld    class [System]System.Collections.Specialized.NameValueCollection <ReadFormDataAsync>d__1::formData
0xbe89  ldarg.0
0xbe8a  ldfld    string <ReadFormDataAsync>d__1::<formFieldName>5__3
0xbe8f  ldloc.3
0xbe90  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xbe95  ldarg.0
0xbe96  ldnull
0xbe97  stfld    string <ReadFormDataAsync>d__1::<formFieldName>5__3
0xbe9c  ldarg.0
0xbe9d  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Net.Http]System.Net.Http.HttpContent> <ReadFormDataAsync>d__1::<>7__wrap1
0xbea2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbea7  brtrue   loc_BDD7
0xbeac  leave.s  loc_BEC6
0xbeae  ldloc.0
0xbeaf  ldc.i4.0
0xbeb0  bge.s    loc_BEC5
0xbeb2  ldarg.0
0xbeb3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Net.Http]System.Net.Http.HttpContent> <ReadFormDataAsync>d__1::<>7__wrap1
0xbeb8  brfalse.s loc_BEC5
0xbeba  ldarg.0
0xbebb  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Net.Http]System.Net.Http.HttpContent> <ReadFormDataAsync>d__1::<>7__wrap1
0xbec0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbec5  endfinally
0xbec6  ldarg.0
0xbec7  ldnull
0xbec8  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Net.Http]System.Net.Http.HttpContent> <ReadFormDataAsync>d__1::<>7__wrap1
0xbecd  leave.s  loc_BEE8
0xbecf  stloc.s  5
0xbed1  ldarg.0
0xbed2  ldc.i4.s 0xFE
0xbed4  stfld    int32 <ReadFormDataAsync>d__1::<>1__state
0xbed9  ldarg.0
0xbeda  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ReadFormDataAsync>d__1::<>t__builder
0xbedf  ldloc.s  5
0xbee1  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0xbee6  leave.s  loc_BEFB
0xbee8  ldarg.0
0xbee9  ldc.i4.s 0xFE
0xbeeb  stfld    int32 <ReadFormDataAsync>d__1::<>1__state
0xbef0  ldarg.0
0xbef1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ReadFormDataAsync>d__1::<>t__builder
0xbef6  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0xbefb  ret
```
