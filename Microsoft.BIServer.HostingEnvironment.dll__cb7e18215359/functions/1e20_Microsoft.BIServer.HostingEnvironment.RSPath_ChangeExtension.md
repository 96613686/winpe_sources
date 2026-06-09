# Microsoft.BIServer.HostingEnvironment.RSPath::ChangeExtension

- ea: `0x1e20`
- end: `0x1e32`
- name: `Microsoft.BIServer.HostingEnvironment.RSPath::ChangeExtension`
- size: `18`
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
0x1e20  ldarg.0
0x1e21  ldfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1e26  ldarg.1
0x1e27  call     string [mscorlib]System.IO.Path::ChangeExtension(string, string)
0x1e2c  newobj   instance void Microsoft.BIServer.HostingEnvironment.RSPath::.ctor(string path)
0x1e31  ret
```
