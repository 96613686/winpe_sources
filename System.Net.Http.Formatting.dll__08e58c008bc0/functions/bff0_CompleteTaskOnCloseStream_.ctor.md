# CompleteTaskOnCloseStream::.ctor

- ea: `0xbff0`
- end: `0xbfff`
- name: `CompleteTaskOnCloseStream::.ctor`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xc060`

## callees

- `0x5250`

## pseudocode

```c

```

## disassembly

```asm
0xbff0  ldarg.0
0xbff1  ldarg.1
0xbff2  call     instance void System.Net.Http.Internal.DelegatingStream::.ctor(class [mscorlib]System.IO.Stream innerStream)
0xbff7  ldarg.0
0xbff8  ldarg.2
0xbff9  stfld    class [mscorlib]System.Threading.Tasks.TaskCompletionSource`1<bool> CompleteTaskOnCloseStream::_serializeToStreamTask
0xbffe  ret
```
