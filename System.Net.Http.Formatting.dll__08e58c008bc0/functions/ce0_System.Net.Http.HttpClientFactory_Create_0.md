# System.Net.Http.HttpClientFactory::Create_0

- ea: `0xce0`
- end: `0xced`
- name: `System.Net.Http.HttpClientFactory::Create_0`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0xcd0`

## callees

- `0xcf0`

## pseudocode

```c

```

## disassembly

```asm
0xce0  ldarg.0
0xce1  ldarg.1
0xce2  call     class [System.Net.Http]System.Net.Http.HttpMessageHandler System.Net.Http.HttpClientFactory::CreatePipeline(class [System.Net.Http]System.Net.Http.HttpMessageHandler innerHandler, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Net.Http]System.Net.Http.DelegatingHandler> handlers)
0xce7  newobj   instance void [System.Net.Http]System.Net.Http.HttpClient::.ctor(class [System.Net.Http]System.Net.Http.HttpMessageHandler)
0xcec  ret
```
