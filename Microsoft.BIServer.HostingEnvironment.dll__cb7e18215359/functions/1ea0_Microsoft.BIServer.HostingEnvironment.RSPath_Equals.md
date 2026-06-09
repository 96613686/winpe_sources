# Microsoft.BIServer.HostingEnvironment.RSPath::Equals

- ea: `0x1ea0`
- end: `0x1eaf`
- name: `Microsoft.BIServer.HostingEnvironment.RSPath::Equals`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1f00`

## pseudocode

```c

```

## disassembly

```asm
0x1ea0  ldarg.1
0x1ea1  isinst   Microsoft.BIServer.HostingEnvironment.RSPath
0x1ea6  stloc.0
0x1ea7  ldarg.0
0x1ea8  ldloc.0
0x1ea9  call     bool Microsoft.BIServer.HostingEnvironment.RSPath::op_Equality(class Microsoft.BIServer.HostingEnvironment.RSPath path1, class Microsoft.BIServer.HostingEnvironment.RSPath path2)
0x1eae  ret
```
