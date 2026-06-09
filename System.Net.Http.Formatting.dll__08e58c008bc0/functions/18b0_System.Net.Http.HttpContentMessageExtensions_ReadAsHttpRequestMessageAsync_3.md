# System.Net.Http.HttpContentMessageExtensions::ReadAsHttpRequestMessageAsync_3

- ea: `0x18b0`
- end: `0x18be`
- name: `System.Net.Http.HttpContentMessageExtensions::ReadAsHttpRequestMessageAsync_3`
- size: `14`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1850`
- `0x1890`

## callees

- `0x18d0`

## pseudocode

```c

```

## disassembly

```asm
0x18b0  ldarg.0
0x18b1  ldarg.1
0x18b2  ldarg.2
0x18b3  ldc.i4   0x4000
0x18b8  call     class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpRequestMessage> System.Net.Http.HttpContentMessageExtensions::ReadAsHttpRequestMessageAsync(class [System.Net.Http]System.Net.Http.HttpContent content, string uriScheme, int32 bufferSize, int32 maxHeaderSize)
0x18bd  ret
```
