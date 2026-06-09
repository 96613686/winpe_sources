# System.Net.Http.HttpClientExtensions::PutAsync_3

- ea: `0x1180`
- end: `0x11a3`
- name: `System.Net.Http.HttpClientExtensions::PutAsync_3`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1180`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x1180  ldarg.0
0x1181  brtrue.s loc_118E
0x1183  ldstr    aClient// "client"
0x1188  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x118d  throw
0x118e  ldarg.2
0x118f  ldarg.3
0x1190  ldarg.s  4
0x1192  newobj   instance void class System.Net.Http.ObjectContent`1<mvar<u1>>::.ctor(var<u1>, !!T0, class System.Net.Http.Formatting.MediaTypeFormatter)
0x1197  stloc.0
0x1198  ldarg.0
0x1199  ldarg.1
0x119a  ldloc.0
0x119b  ldarg.s  5
0x119d  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> [System.Net.Http]System.Net.Http.HttpClient::PutAsync(string, class [System.Net.Http]System.Net.Http.HttpContent, valuetype [mscorlib]System.Threading.CancellationToken)
0x11a2  ret
```
