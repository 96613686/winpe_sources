# Microsoft.BIServer.HostingEnvironment.RSPath::op_Addition

- ea: `0x1eb0`
- end: `0x1ec2`
- name: `Microsoft.BIServer.HostingEnvironment.RSPath::op_Addition`
- size: `18`
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
0x1eb0  ldarg.0
0x1eb1  ldfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1eb6  ldarg.1
0x1eb7  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1ebc  newobj   instance void Microsoft.BIServer.HostingEnvironment.RSPath::.ctor(string path)
0x1ec1  ret
```
