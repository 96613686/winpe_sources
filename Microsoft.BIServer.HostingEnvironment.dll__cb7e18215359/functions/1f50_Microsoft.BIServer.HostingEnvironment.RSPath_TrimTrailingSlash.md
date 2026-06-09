# Microsoft.BIServer.HostingEnvironment.RSPath::TrimTrailingSlash

- ea: `0x1f50`
- end: `0x1f80`
- name: `Microsoft.BIServer.HostingEnvironment.RSPath::TrimTrailingSlash`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1d20`
- `0x1f50`

## pseudocode

```c

```

## disassembly

```asm
0x1f50  ldarg.0
0x1f51  ldfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1f56  ldstr    asc_82D8// "\\"
0x1f5b  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x1f60  brtrue.s loc_1F64
0x1f62  ldarg.0
0x1f63  ret
0x1f64  ldarg.0
0x1f65  ldfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1f6a  ldc.i4.1
0x1f6b  newarr   [mscorlib]System.Char
0x1f70  dup
0x1f71  ldc.i4.0
0x1f72  ldc.i4.s 0x5C
0x1f74  stelem.i2
0x1f75  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x1f7a  newobj   instance void Microsoft.BIServer.HostingEnvironment.RSPath::.ctor(string path)
0x1f7f  ret
```
