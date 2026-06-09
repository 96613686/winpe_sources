# System.Net.Http.Handlers.ProgressStream::ReadByte

- ea: `0x4610`
- end: `0x462d`
- name: `System.Net.Http.Handlers.ProgressStream::ReadByte`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x4610`
- `0x4850`
- `0x5270`

## pseudocode

```c

```

## disassembly

```asm
0x4610  ldarg.0
0x4611  call     instance class [mscorlib]System.IO.Stream System.Net.Http.Internal.DelegatingStream::get_InnerStream()
0x4616  callvirt instance int32 [mscorlib]System.IO.Stream::ReadByte()
0x461b  stloc.0
0x461c  ldarg.0
0x461d  ldloc.0
0x461e  ldc.i4.m1
0x461f  beq.s    loc_4624
0x4621  ldc.i4.1
0x4622  br.s     loc_4625
0x4624  ldc.i4.0
0x4625  ldnull
0x4626  call     instance void System.Net.Http.Handlers.ProgressStream::ReportBytesReceived(int32 bytesReceived, object userState)
0x462b  ldloc.0
0x462c  ret
```
