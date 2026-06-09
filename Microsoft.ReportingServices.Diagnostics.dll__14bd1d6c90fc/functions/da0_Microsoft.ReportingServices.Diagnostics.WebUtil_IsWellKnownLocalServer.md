# Microsoft.ReportingServices.Diagnostics.WebUtil::IsWellKnownLocalServer

- ea: `0xda0`
- end: `0xe12`
- name: `Microsoft.ReportingServices.Diagnostics.WebUtil::IsWellKnownLocalServer`
- size: `114`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb10`
- `0xe60`
- `0xc990`

## callees

- `0xda0`

## pseudocode

```c

```

## disassembly

```asm
0xda0  ldarg.0
0xda1  ldstr    aLocalhost// "localhost"
0xda6  ldc.i4.5
0xda7  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xdac  brtrue.s loc_DB0
0xdae  ldc.i4.1
0xdaf  ret
0xdb0  ldarg.0
0xdb1  ldstr    aLocal// "(local)"
0xdb6  ldc.i4.5
0xdb7  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xdbc  brtrue.s loc_DC0
0xdbe  ldc.i4.1
0xdbf  ret
0xdc0  ldarg.0
0xdc1  ldstr    asc_122DC// "."
0xdc6  ldc.i4.5
0xdc7  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xdcc  brtrue.s loc_DD0
0xdce  ldc.i4.1
0xdcf  ret
0xdd0  ldarg.0
0xdd1  call     string [mscorlib]System.Environment::get_MachineName()
0xdd6  ldc.i4.5
0xdd7  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xddc  brtrue.s loc_DE0
0xdde  ldc.i4.1
0xddf  ret
0xde0  ldarg.0
0xde1  ldstr    a127001// "127.0.0.1"
0xde6  ldc.i4.5
0xde7  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xdec  brtrue.s loc_DF0
0xdee  ldc.i4.1
0xdef  ret
0xdf0  ldarg.0
0xdf1  ldstr    a1// "::1"
0xdf6  ldc.i4.5
0xdf7  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xdfc  brtrue.s loc_E00
0xdfe  ldc.i4.1
0xdff  ret
0xe00  ldarg.0
0xe01  ldstr    a1_0// "[::1]"
0xe06  ldc.i4.5
0xe07  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xe0c  brtrue.s loc_E10
0xe0e  ldc.i4.1
0xe0f  ret
0xe10  ldc.i4.0
0xe11  ret
```
