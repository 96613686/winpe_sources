# Microsoft.BIServer.HostingEnvironment.RSPath::get_FileName

- ea: `0x1d70`
- end: `0x1d81`
- name: `Microsoft.BIServer.HostingEnvironment.RSPath::get_FileName`
- size: `17`
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
0x1d70  ldarg.0
0x1d71  ldfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1d76  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x1d7b  newobj   instance void Microsoft.BIServer.HostingEnvironment.RSPath::.ctor(string path)
0x1d80  ret
```
