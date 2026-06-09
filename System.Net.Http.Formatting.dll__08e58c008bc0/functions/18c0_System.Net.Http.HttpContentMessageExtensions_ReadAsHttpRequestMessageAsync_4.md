# System.Net.Http.HttpContentMessageExtensions::ReadAsHttpRequestMessageAsync_4

- ea: `0x18c0`
- end: `0x18cf`
- name: `System.Net.Http.HttpContentMessageExtensions::ReadAsHttpRequestMessageAsync_4`
- size: `15`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1870`
- `0x18a0`

## callees

- `0x18e0`

## pseudocode

```c

```

## disassembly

```asm
0x18c0  ldarg.0
0x18c1  ldarg.1
0x18c2  ldarg.2
0x18c3  ldc.i4   0x4000
0x18c8  ldarg.3
0x18c9  call     class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpRequestMessage> System.Net.Http.HttpContentMessageExtensions::ReadAsHttpRequestMessageAsync(class [System.Net.Http]System.Net.Http.HttpContent content, string uriScheme, int32 bufferSize, int32 maxHeaderSize, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x18ce  ret
```
