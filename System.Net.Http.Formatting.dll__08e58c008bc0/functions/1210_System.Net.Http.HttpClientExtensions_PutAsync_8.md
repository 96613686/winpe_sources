# System.Net.Http.HttpClientExtensions::PutAsync_8

- ea: `0x1210`
- end: `0x1233`
- name: `System.Net.Http.HttpClientExtensions::PutAsync_8`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1210`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x1210  ldarg.0
0x1211  brtrue.s loc_121E
0x1213  ldstr    aClient// "client"
0x1218  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x121d  throw
0x121e  ldarg.2
0x121f  ldarg.3
0x1220  ldarg.s  4
0x1222  newobj   instance void class System.Net.Http.ObjectContent`1<mvar<u1>>::.ctor(var<u1>, !!T0, class System.Net.Http.Formatting.MediaTypeFormatter)
0x1227  stloc.0
0x1228  ldarg.0
0x1229  ldarg.1
0x122a  ldloc.0
0x122b  ldarg.s  5
0x122d  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> [System.Net.Http]System.Net.Http.HttpClient::PutAsync(class [System]System.Uri, class [System.Net.Http]System.Net.Http.HttpContent, valuetype [mscorlib]System.Threading.CancellationToken)
0x1232  ret
```
