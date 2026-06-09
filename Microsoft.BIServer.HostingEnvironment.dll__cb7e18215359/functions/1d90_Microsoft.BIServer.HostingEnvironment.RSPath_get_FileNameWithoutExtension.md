# Microsoft.BIServer.HostingEnvironment.RSPath::get_FileNameWithoutExtension

- ea: `0x1d90`
- end: `0x1da1`
- name: `Microsoft.BIServer.HostingEnvironment.RSPath::get_FileNameWithoutExtension`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1d20`

## pseudocode

```c

```

## disassembly

```asm
0x1d90  ldarg.0
0x1d91  ldfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1d96  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x1d9b  newobj   instance void Microsoft.BIServer.HostingEnvironment.RSPath::.ctor(string path)
0x1da0  ret
```
