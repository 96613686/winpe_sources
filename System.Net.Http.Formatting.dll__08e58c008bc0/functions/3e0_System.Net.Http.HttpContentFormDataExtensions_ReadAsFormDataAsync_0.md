# System.Net.Http.HttpContentFormDataExtensions::ReadAsFormDataAsync_0

- ea: `0x3e0`
- end: `0x406`
- name: `System.Net.Http.HttpContentFormDataExtensions::ReadAsFormDataAsync_0`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x3d0`

## callees

- `0x3e0`
- `0x410`
- `0x7440`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x3e0  ldarg.0
0x3e1  brtrue.s loc_3EE
0x3e3  ldstr    aContent// "content"
0x3e8  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x3ed  throw
0x3ee  ldc.i4.1
0x3ef  newarr   System.Net.Http.Formatting.MediaTypeFormatter
0x3f4  dup
0x3f5  ldc.i4.0
0x3f6  newobj   instance void System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::.ctor()
0x3fb  stelem.ref
0x3fc  stloc.0
0x3fd  ldarg.0
0x3fe  ldloc.0
0x3ff  ldarg.1
0x400  call     class [mscorlib]System.Threading.Tasks.Task`1<class [System]System.Collections.Specialized.NameValueCollection> System.Net.Http.HttpContentFormDataExtensions::ReadAsAsyncCore(class [System.Net.Http]System.Net.Http.HttpContent content, class System.Net.Http.Formatting.MediaTypeFormatter[] formatters, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x405  ret
```
