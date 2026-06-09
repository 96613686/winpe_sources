# System.Net.Http.FormattingUtilities::UnquoteToken

- ea: `0x1350`
- end: `0x1391`
- name: `System.Net.Http.FormattingUtilities::UnquoteToken`
- size: `65`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x990`
- `0x2070`
- `0x3fc0`
- `0xa8a0`
- `0xbdb0`
- `0xbf70`

## callees

- `0x1350`

## pseudocode

```c

```

## disassembly

```asm
0x1350  ldarg.0
0x1351  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1356  brfalse.s loc_135A
0x1358  ldarg.0
0x1359  ret
0x135a  ldarg.0
0x135b  ldstr    asc_F268// "\""
0x1360  ldc.i4.4
0x1361  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x1366  brfalse.s loc_138F
0x1368  ldarg.0
0x1369  ldstr    asc_F268// "\""
0x136e  ldc.i4.4
0x136f  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x1374  brfalse.s loc_138F
0x1376  ldarg.0
0x1377  callvirt instance int32 [mscorlib]System.String::get_Length()
0x137c  ldc.i4.1
0x137d  ble.s    loc_138F
0x137f  ldarg.0
0x1380  ldc.i4.1
0x1381  ldarg.0
0x1382  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1387  ldc.i4.2
0x1388  sub
0x1389  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x138e  ret
0x138f  ldarg.0
0x1390  ret
```
