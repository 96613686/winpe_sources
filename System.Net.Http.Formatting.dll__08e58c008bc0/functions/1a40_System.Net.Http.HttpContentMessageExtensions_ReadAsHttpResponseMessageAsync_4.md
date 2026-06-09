# System.Net.Http.HttpContentMessageExtensions::ReadAsHttpResponseMessageAsync_4

- ea: `0x1a40`
- end: `0x1a9f`
- name: `System.Net.Http.HttpContentMessageExtensions::ReadAsHttpResponseMessageAsync_4`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1a20`
- `0x1a30`

## callees

- `0x1a40`
- `0x1aa0`
- `0x2070`
- `0xb3c0`
- `0xb410`

## pseudocode

```c

```

## disassembly

```asm
0x1a40  ldarg.0
0x1a41  brtrue.s loc_1A4E
0x1a43  ldstr    aContent// "content"
0x1a48  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x1a4d  throw
0x1a4e  ldarg.1
0x1a4f  ldc.i4   0x100
0x1a54  bge.s    loc_1A71
0x1a56  ldstr    aBuffersize// "bufferSize"
0x1a5b  ldarg.1
0x1a5c  box      [mscorlib]System.Int32
0x1a61  ldc.i4   0x100
0x1a66  box      [mscorlib]System.Int32
0x1a6b  call     class [mscorlib]System.ArgumentOutOfRangeException System.Web.Http.Error::ArgumentMustBeGreaterThanOrEqualTo(string parameterName, object actualValue, object minValue)
0x1a70  throw
0x1a71  ldarg.2
0x1a72  ldc.i4.2
0x1a73  bge.s    loc_1A8C
0x1a75  ldstr    aMaxheadersize// "maxHeaderSize"
0x1a7a  ldarg.2
0x1a7b  box      [mscorlib]System.Int32
0x1a80  ldc.i4.2
0x1a81  box      [mscorlib]System.Int32
0x1a86  call     class [mscorlib]System.ArgumentOutOfRangeException System.Web.Http.Error::ArgumentMustBeGreaterThanOrEqualTo(string parameterName, object actualValue, object minValue)
0x1a8b  throw
0x1a8c  ldarg.0
0x1a8d  ldc.i4.0
0x1a8e  ldc.i4.1
0x1a8f  call     bool System.Net.Http.HttpMessageContent::ValidateHttpMessageContent(class [System.Net.Http]System.Net.Http.HttpContent content, bool isRequest, bool throwOnError)
0x1a94  pop
0x1a95  ldarg.0
0x1a96  ldarg.1
0x1a97  ldarg.2
0x1a98  ldarg.3
0x1a99  call     class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> System.Net.Http.HttpContentMessageExtensions::ReadAsHttpResponseMessageAsyncCore(class [System.Net.Http]System.Net.Http.HttpContent content, int32 bufferSize, int32 maxHeaderSize, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x1a9e  ret
```
