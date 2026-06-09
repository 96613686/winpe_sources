# Microsoft.BIServer.HostingEnvironment.RSPath::op_Inequality

- ea: `0x1f30`
- end: `0x1f3b`
- name: `Microsoft.BIServer.HostingEnvironment.RSPath::op_Inequality`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1ed0`

## callees

- `0x1f00`

## pseudocode

```c

```

## disassembly

```asm
0x1f30  ldarg.0
0x1f31  ldarg.1
0x1f32  call     bool Microsoft.BIServer.HostingEnvironment.RSPath::op_Equality(class Microsoft.BIServer.HostingEnvironment.RSPath path1, class Microsoft.BIServer.HostingEnvironment.RSPath path2)
0x1f37  ldc.i4.0
0x1f38  ceq
0x1f3a  ret
```
