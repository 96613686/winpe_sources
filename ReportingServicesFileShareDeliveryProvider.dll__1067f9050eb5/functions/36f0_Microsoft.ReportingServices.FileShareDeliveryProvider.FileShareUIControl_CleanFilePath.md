# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::CleanFilePath

- ea: `0x36f0`
- end: `0x3718`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::CleanFilePath`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2350`
- `0x2430`
- `0x4100`

## callees

- `0x36f0`

## pseudocode

```c

```

## disassembly

```asm
0x36f0  ldarg.0
0x36f1  callvirt instance string [mscorlib]System.String::Trim()
0x36f6  stloc.0
0x36f7  ldloc.0
0x36f8  ldstr    asc_55E6// "\\"
0x36fd  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x3702  brfalse.s loc_3716
0x3704  ldloc.0
0x3705  ldc.i4.1
0x3706  newarr   [mscorlib]System.Char
0x370b  dup
0x370c  ldc.i4.0
0x370d  ldc.i4.s 0x5C
0x370f  stelem.i2
0x3710  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x3715  stloc.0
0x3716  ldloc.0
0x3717  ret
```
