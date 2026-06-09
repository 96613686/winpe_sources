# Microsoft.BIServer.HostingEnvironment.RSPath::op_Implicit_0

- ea: `0x1ef0`
- end: `0x1efc`
- name: `Microsoft.BIServer.HostingEnvironment.RSPath::op_Implicit_0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1d20`
- `0x1ef0`

## pseudocode

```c

```

## disassembly

```asm
0x1ef0  ldarg.0
0x1ef1  brtrue.s loc_1EF5
0x1ef3  ldnull
0x1ef4  ret
0x1ef5  ldarg.0
0x1ef6  newobj   instance void Microsoft.BIServer.HostingEnvironment.RSPath::.ctor(string path)
0x1efb  ret
```
