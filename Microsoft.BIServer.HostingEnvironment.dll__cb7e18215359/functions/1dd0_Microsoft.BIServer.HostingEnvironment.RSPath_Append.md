# Microsoft.BIServer.HostingEnvironment.RSPath::Append

- ea: `0x1dd0`
- end: `0x1e0d`
- name: `Microsoft.BIServer.HostingEnvironment.RSPath::Append`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1d20`
- `0x1dd0`

## pseudocode

```c

```

## disassembly

```asm
0x1dd0  ldarg.0
0x1dd1  ldfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1dd6  stloc.0
0x1dd7  ldarg.0
0x1dd8  ldfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1ddd  call     string [mscorlib]System.IO.Path::GetPathRoot(string)
0x1de2  ldarg.0
0x1de3  ldfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1de8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1ded  brfalse.s loc_1E00
0x1def  ldarg.0
0x1df0  ldfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1df5  ldstr    asc_82D8// "\\"
0x1dfa  call     string [mscorlib]System.String::Concat(string, string)
0x1dff  stloc.0
0x1e00  ldloc.0
0x1e01  ldarg.1
0x1e02  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1e07  newobj   instance void Microsoft.BIServer.HostingEnvironment.RSPath::.ctor(string path)
0x1e0c  ret
```
