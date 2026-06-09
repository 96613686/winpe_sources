# Microsoft.BIServer.HostingEnvironment.RSPath::get_FullPath

- ea: `0x1db0`
- end: `0x1dc1`
- name: `Microsoft.BIServer.HostingEnvironment.RSPath::get_FullPath`
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
0x1db0  ldarg.0
0x1db1  ldfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1db6  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x1dbb  newobj   instance void Microsoft.BIServer.HostingEnvironment.RSPath::.ctor(string path)
0x1dc0  ret
```
