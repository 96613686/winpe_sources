# Microsoft.BIServer.Management.WebHost.RequestLoggingMiddleWare::.cctor

- ea: `0x2c0`
- end: `0x2d4`
- name: `Microsoft.BIServer.Management.WebHost.RequestLoggingMiddleWare::.cctor`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2c0  ldc.i4.1
0x2c1  newarr   [mscorlib]System.String
0x2c6  dup
0x2c7  ldc.i4.0
0x2c8  ldstr    aManagementstat// "/ManagementState"
0x2cd  stelem.ref
0x2ce  stsfld   string[] Microsoft.BIServer.Management.WebHost.RequestLoggingMiddleWare::LogRoutesAsTrace
0x2d3  ret
```
