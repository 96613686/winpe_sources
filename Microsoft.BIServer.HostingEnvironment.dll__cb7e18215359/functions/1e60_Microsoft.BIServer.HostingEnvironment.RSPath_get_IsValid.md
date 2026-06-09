# Microsoft.BIServer.HostingEnvironment.RSPath::get_IsValid

- ea: `0x1e60`
- end: `0x1e81`
- name: `Microsoft.BIServer.HostingEnvironment.RSPath::get_IsValid`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1e60`

## pseudocode

```c

```

## disassembly

```asm
0x1e60  ldarg.0
0x1e61  ldfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1e66  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x1e6b  pop
0x1e6c  leave.s  loc_1E78
0x1e6e  pop
0x1e6f  ldc.i4.0
0x1e70  box      [mscorlib]System.Boolean
0x1e75  stloc.0
0x1e76  leave.s  loc_1E7F
0x1e78  ldc.i4.1
0x1e79  box      [mscorlib]System.Boolean
0x1e7e  ret
0x1e7f  ldloc.0
0x1e80  ret
```
