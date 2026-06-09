# Microsoft.BIServer.HostingEnvironment.RSPath::op_Equality

- ea: `0x1f00`
- end: `0x1f24`
- name: `Microsoft.BIServer.HostingEnvironment.RSPath::op_Equality`
- size: `36`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1ea0`
- `0x1f30`
- `0x1f40`

## callees

- `0x1f00`

## pseudocode

```c

```

## disassembly

```asm
0x1f00  ldarg.0
0x1f01  ldarg.1
0x1f02  bne.un.s loc_1F06
0x1f04  ldc.i4.1
0x1f05  ret
0x1f06  ldarg.0
0x1f07  brfalse.s loc_1F0C
0x1f09  ldarg.1
0x1f0a  brtrue.s loc_1F0E
0x1f0c  ldc.i4.0
0x1f0d  ret
0x1f0e  ldarg.0
0x1f0f  ldfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1f14  ldarg.1
0x1f15  ldfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1f1a  ldc.i4.3
0x1f1b  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1f20  ldc.i4.0
0x1f21  ceq
0x1f23  ret
```
