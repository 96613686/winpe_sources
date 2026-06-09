# System.Net.Http.Handlers.ProgressStream::Write

- ea: `0x46d0`
- end: `0x46e7`
- name: `System.Net.Http.Handlers.ProgressStream::Write`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x47a0`
- `0x5270`

## pseudocode

```c

```

## disassembly

```asm
0x46d0  ldarg.0
0x46d1  call     instance class [mscorlib]System.IO.Stream System.Net.Http.Internal.DelegatingStream::get_InnerStream()
0x46d6  ldarg.1
0x46d7  ldarg.2
0x46d8  ldarg.3
0x46d9  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x46de  ldarg.0
0x46df  ldarg.3
0x46e0  ldnull
0x46e1  call     instance void System.Net.Http.Handlers.ProgressStream::ReportBytesSent(int32 bytesSent, object userState)
0x46e6  ret
```
