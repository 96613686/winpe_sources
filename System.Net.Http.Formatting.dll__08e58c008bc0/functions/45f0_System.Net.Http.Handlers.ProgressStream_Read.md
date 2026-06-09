# System.Net.Http.Handlers.ProgressStream::Read

- ea: `0x45f0`
- end: `0x4609`
- name: `System.Net.Http.Handlers.ProgressStream::Read`
- size: `25`
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
0x45f0  ldarg.0
0x45f1  call     instance class [mscorlib]System.IO.Stream System.Net.Http.Internal.DelegatingStream::get_InnerStream()
0x45f6  ldarg.1
0x45f7  ldarg.2
0x45f8  ldarg.3
0x45f9  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x45fe  stloc.0
0x45ff  ldarg.0
0x4600  ldloc.0
0x4601  ldnull
0x4602  call     instance void System.Net.Http.Handlers.ProgressStream::ReportBytesReceived(int32 bytesReceived, object userState)
0x4607  ldloc.0
0x4608  ret
```
