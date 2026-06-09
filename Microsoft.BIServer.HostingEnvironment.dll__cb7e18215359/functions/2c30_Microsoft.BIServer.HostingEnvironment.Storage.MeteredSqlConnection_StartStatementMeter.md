# Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::StartStatementMeter

- ea: `0x2c30`
- end: `0x2c5c`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::StartStatementMeter`
- size: `44`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5f20`
- `0x6070`
- `0x6510`

## callees

- `0x1be0`
- `0x2c60`

## pseudocode

```c

```

## disassembly

```asm
0x2c30  ldarg.0
0x2c31  call     instance void Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::StopStatementMeter()
0x2c36  ldarg.0
0x2c37  ldc.i4.3
0x2c38  newarr   [mscorlib]System.String
0x2c3d  dup
0x2c3e  ldc.i4.0
0x2c3f  ldstr    aSql// "SQL"
0x2c44  stelem.ref
0x2c45  dup
0x2c46  ldc.i4.1
0x2c47  ldstr    aSegment// "segment"
0x2c4c  stelem.ref
0x2c4d  dup
0x2c4e  ldc.i4.2
0x2c4f  ldarg.1
0x2c50  stelem.ref
0x2c51  call     class [mscorlib]System.IDisposable Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[] names)
0x2c56  stfld    class [mscorlib]System.IDisposable Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::_statementMeter
0x2c5b  ret
```
