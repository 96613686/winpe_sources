# Microsoft.BIServer.HostingEnvironment.RSPath::op_Implicit

- ea: `0x1ed0`
- end: `0x1ee2`
- name: `Microsoft.BIServer.HostingEnvironment.RSPath::op_Implicit`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1ed0`
- `0x1f30`

## pseudocode

```c

```

## disassembly

```asm
0x1ed0  ldarg.0
0x1ed1  ldnull
0x1ed2  call     bool Microsoft.BIServer.HostingEnvironment.RSPath::op_Inequality(class Microsoft.BIServer.HostingEnvironment.RSPath path1, class Microsoft.BIServer.HostingEnvironment.RSPath path2)
0x1ed7  brtrue.s loc_1EDB
0x1ed9  ldnull
0x1eda  ret
0x1edb  ldarg.0
0x1edc  ldfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1ee1  ret
```
