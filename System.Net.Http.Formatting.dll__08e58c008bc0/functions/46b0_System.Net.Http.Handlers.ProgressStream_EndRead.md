# System.Net.Http.Handlers.ProgressStream::EndRead

- ea: `0x46b0`
- end: `0x46cc`
- name: `System.Net.Http.Handlers.ProgressStream::EndRead`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x4850`
- `0x5270`

## pseudocode

```c

```

## disassembly

```asm
0x46b0  ldarg.0
0x46b1  call     instance class [mscorlib]System.IO.Stream System.Net.Http.Internal.DelegatingStream::get_InnerStream()
0x46b6  ldarg.1
0x46b7  callvirt instance int32 [mscorlib]System.IO.Stream::EndRead(class [mscorlib]System.IAsyncResult)
0x46bc  stloc.0
0x46bd  ldarg.0
0x46be  ldloc.0
0x46bf  ldarg.1
0x46c0  callvirt instance object [mscorlib]System.IAsyncResult::get_AsyncState()
0x46c5  call     instance void System.Net.Http.Handlers.ProgressStream::ReportBytesReceived(int32 bytesReceived, object userState)
0x46ca  ldloc.0
0x46cb  ret
```
