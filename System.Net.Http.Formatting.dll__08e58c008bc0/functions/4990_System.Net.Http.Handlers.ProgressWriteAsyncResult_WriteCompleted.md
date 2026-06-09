# System.Net.Http.Handlers.ProgressWriteAsyncResult::WriteCompleted

- ea: `0x4990`
- end: `0x49c0`
- name: `System.Net.Http.Handlers.ProgressWriteAsyncResult::WriteCompleted`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x4910`
- `0x4960`

## callees

- `0x47a0`
- `0x50b0`
- `0x5100`

## pseudocode

```c

```

## disassembly

```asm
0x4990  ldarg.0
0x4991  ldfld    class [mscorlib]System.IO.Stream System.Net.Http.Handlers.ProgressWriteAsyncResult::_innerStream
0x4996  ldarg.1
0x4997  callvirt instance void [mscorlib]System.IO.Stream::EndWrite(class [mscorlib]System.IAsyncResult)
0x499c  ldarg.0
0x499d  ldfld    class System.Net.Http.Handlers.ProgressStream System.Net.Http.Handlers.ProgressWriteAsyncResult::_progressStream
0x49a2  ldarg.0
0x49a3  ldfld    int32 System.Net.Http.Handlers.ProgressWriteAsyncResult::_count
0x49a8  ldarg.0
0x49a9  call     instance object System.Net.Http.Internal.AsyncResult::get_AsyncState()
0x49ae  callvirt instance void System.Net.Http.Handlers.ProgressStream::ReportBytesSent(int32 bytesSent, object userState)
0x49b3  ldarg.0
0x49b4  ldarg.1
0x49b5  callvirt instance bool [mscorlib]System.IAsyncResult::get_CompletedSynchronously()
0x49ba  call     instance void System.Net.Http.Internal.AsyncResult::Complete(bool completedSynchronously)
0x49bf  ret
```
