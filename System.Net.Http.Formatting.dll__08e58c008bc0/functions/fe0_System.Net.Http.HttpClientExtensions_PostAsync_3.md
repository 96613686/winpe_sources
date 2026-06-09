# System.Net.Http.HttpClientExtensions::PostAsync_3

- ea: `0xfe0`
- end: `0x1003`
- name: `System.Net.Http.HttpClientExtensions::PostAsync_3`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0xfe0`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0xfe0  ldarg.0
0xfe1  brtrue.s loc_FEE
0xfe3  ldstr    aClient// "client"
0xfe8  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0xfed  throw
0xfee  ldarg.2
0xfef  ldarg.3
0xff0  ldarg.s  4
0xff2  newobj   instance void class System.Net.Http.ObjectContent`1<mvar<u1>>::.ctor(var<u1>, !!T0, class System.Net.Http.Formatting.MediaTypeFormatter)
0xff7  stloc.0
0xff8  ldarg.0
0xff9  ldarg.1
0xffa  ldloc.0
0xffb  ldarg.s  5
0xffd  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> [System.Net.Http]System.Net.Http.HttpClient::PostAsync(string, class [System.Net.Http]System.Net.Http.HttpContent, valuetype [mscorlib]System.Threading.CancellationToken)
0x1002  ret
```
