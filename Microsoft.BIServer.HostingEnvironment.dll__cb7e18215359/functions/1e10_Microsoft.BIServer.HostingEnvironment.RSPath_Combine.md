# Microsoft.BIServer.HostingEnvironment.RSPath::Combine

- ea: `0x1e10`
- end: `0x1e1c`
- name: `Microsoft.BIServer.HostingEnvironment.RSPath::Combine`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1d20`

## pseudocode

```c

```

## disassembly

```asm
0x1e10  ldarg.0
0x1e11  call     string [mscorlib]System.IO.Path::Combine(string[])
0x1e16  newobj   instance void Microsoft.BIServer.HostingEnvironment.RSPath::.ctor(string path)
0x1e1b  ret
```
