# System.Net.Http.Handlers.ProgressStream::BeginWrite

- ea: `0x4770`
- end: `0x4784`
- name: `System.Net.Http.Handlers.ProgressStream::BeginWrite`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x4910`
- `0x5270`

## pseudocode

```c

```

## disassembly

```asm
0x4770  ldarg.0
0x4771  call     instance class [mscorlib]System.IO.Stream System.Net.Http.Internal.DelegatingStream::get_InnerStream()
0x4776  ldarg.0
0x4777  ldarg.1
0x4778  ldarg.2
0x4779  ldarg.3
0x477a  ldarg.s  4
0x477c  ldarg.s  5
0x477e  newobj   instance void System.Net.Http.Handlers.ProgressWriteAsyncResult::.ctor(class [mscorlib]System.IO.Stream innerStream, class System.Net.Http.Handlers.ProgressStream progressStream, unsigned int8[] buffer, int32 offset, int32 count, class [mscorlib]System.AsyncCallback callback, object state)
0x4783  ret
```
