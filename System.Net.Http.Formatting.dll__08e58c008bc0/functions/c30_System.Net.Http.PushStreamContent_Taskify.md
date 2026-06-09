# System.Net.Http.PushStreamContent::Taskify

- ea: `0xc30`
- end: `0xc5b`
- name: `System.Net.Http.PushStreamContent::Taskify`
- size: `43`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0xb90`
- `0xbb0`
- `0xbe0`

## callees

- `0xc30`
- `0xb3c0`
- `0xc020`

## pseudocode

```c

```

## disassembly

```asm
0xc30  newobj   instance void <>c__DisplayClass7_0::.ctor()
0xc35  dup
0xc36  ldarg.0
0xc37  stfld    class [mscorlib]System.Action`3<class [mscorlib]System.IO.Stream, class [System.Net.Http]System.Net.Http.HttpContent, class [System]System.Net.TransportContext> <>c__DisplayClass7_0::onStreamAvailable
0xc3c  dup
0xc3d  ldfld    class [mscorlib]System.Action`3<class [mscorlib]System.IO.Stream, class [System.Net.Http]System.Net.Http.HttpContent, class [System]System.Net.TransportContext> <>c__DisplayClass7_0::onStreamAvailable
0xc42  brtrue.s loc_C4F
0xc44  ldstr    aOnstreamavaila// "onStreamAvailable"
0xc49  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0xc4e  throw
0xc4f  ldftn    instance class [mscorlib]System.Threading.Tasks.Task <>c__DisplayClass7_0::<Taskify>b__0(class [mscorlib]System.IO.Stream stream, class [System.Net.Http]System.Net.Http.HttpContent content, class [System]System.Net.TransportContext transportContext)
0xc55  newobj   instance void class [mscorlib]System.Func`4<class [mscorlib]System.IO.Stream, class [System.Net.Http]System.Net.Http.HttpContent, class [System]System.Net.TransportContext, class [mscorlib]System.Threading.Tasks.Task>::.ctor(object, native int)
0xc5a  ret
```
