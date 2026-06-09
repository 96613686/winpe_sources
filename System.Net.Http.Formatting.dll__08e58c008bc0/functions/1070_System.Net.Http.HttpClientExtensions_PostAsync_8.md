# System.Net.Http.HttpClientExtensions::PostAsync_8

- ea: `0x1070`
- end: `0x1093`
- name: `System.Net.Http.HttpClientExtensions::PostAsync_8`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1070`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x1070  ldarg.0
0x1071  brtrue.s loc_107E
0x1073  ldstr    aClient// "client"
0x1078  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x107d  throw
0x107e  ldarg.2
0x107f  ldarg.3
0x1080  ldarg.s  4
0x1082  newobj   instance void class System.Net.Http.ObjectContent`1<mvar<u1>>::.ctor(var<u1>, !!T0, class System.Net.Http.Formatting.MediaTypeFormatter)
0x1087  stloc.0
0x1088  ldarg.0
0x1089  ldarg.1
0x108a  ldloc.0
0x108b  ldarg.s  5
0x108d  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> [System.Net.Http]System.Net.Http.HttpClient::PostAsync(class [System]System.Uri, class [System.Net.Http]System.Net.Http.HttpContent, valuetype [mscorlib]System.Threading.CancellationToken)
0x1092  ret
```
