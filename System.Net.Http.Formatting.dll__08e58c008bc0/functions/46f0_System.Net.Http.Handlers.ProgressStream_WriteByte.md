# System.Net.Http.Handlers.ProgressStream::WriteByte

- ea: `0x46f0`
- end: `0x4705`
- name: `System.Net.Http.Handlers.ProgressStream::WriteByte`
- size: `21`
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
0x46f0  ldarg.0
0x46f1  call     instance class [mscorlib]System.IO.Stream System.Net.Http.Internal.DelegatingStream::get_InnerStream()
0x46f6  ldarg.1
0x46f7  callvirt instance void [mscorlib]System.IO.Stream::WriteByte(unsigned int8)
0x46fc  ldarg.0
0x46fd  ldc.i4.1
0x46fe  ldnull
0x46ff  call     instance void System.Net.Http.Handlers.ProgressStream::ReportBytesSent(int32 bytesSent, object userState)
0x4704  ret
```
