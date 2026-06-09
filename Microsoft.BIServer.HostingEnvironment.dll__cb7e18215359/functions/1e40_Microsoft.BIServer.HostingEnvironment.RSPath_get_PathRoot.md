# Microsoft.BIServer.HostingEnvironment.RSPath::get_PathRoot

- ea: `0x1e40`
- end: `0x1e51`
- name: `Microsoft.BIServer.HostingEnvironment.RSPath::get_PathRoot`
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
0x1e40  ldarg.0
0x1e41  ldfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1e46  call     string [mscorlib]System.IO.Path::GetPathRoot(string)
0x1e4b  newobj   instance void Microsoft.BIServer.HostingEnvironment.RSPath::.ctor(string path)
0x1e50  ret
```
