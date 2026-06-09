# Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::NowFileTime

- ea: `0x3300`
- end: `0x330e`
- name: `Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::NowFileTime`
- size: `14`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3320`
- `0x3330`

## callees

- `0x32f0`

## pseudocode

```c

```

## disassembly

```asm
0x3300  call     valuetype [mscorlib]System.DateTime Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::NowTime()
0x3305  stloc.0
0x3306  ldloca.s 0
0x3308  call     instance int64 [mscorlib]System.DateTime::ToFileTime()
0x330d  ret
```
