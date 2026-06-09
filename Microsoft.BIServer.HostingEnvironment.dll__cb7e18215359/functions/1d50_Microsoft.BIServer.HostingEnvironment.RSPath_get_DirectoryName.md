# Microsoft.BIServer.HostingEnvironment.RSPath::get_DirectoryName

- ea: `0x1d50`
- end: `0x1d61`
- name: `Microsoft.BIServer.HostingEnvironment.RSPath::get_DirectoryName`
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
0x1d50  ldarg.0
0x1d51  ldfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1d56  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x1d5b  newobj   instance void Microsoft.BIServer.HostingEnvironment.RSPath::.ctor(string path)
0x1d60  ret
```
