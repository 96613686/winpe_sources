# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::IsValidPath

- ea: `0x18e0`
- end: `0x1945`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::IsValidPath`
- size: `101`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe10`
- `0x2350`
- `0x4100`

## callees

- `0x18e0`

## pseudocode

```c

```

## disassembly

```asm
0x18e0  ldarg.0
0x18e1  brfalse.s loc_1943
0x18e3  ldarg.0
0x18e4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x18e9  ldc.i4.2
0x18ea  blt.s    loc_1943
0x18ec  ldarg.0
0x18ed  ldc.i4.0
0x18ee  ldc.i4.2
0x18ef  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x18f4  ldstr    asc_55E0// "\\\\"
0x18f9  ldc.i4.4
0x18fa  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x18ff  brtrue.s loc_193F
0x1901  ldarg.0
0x1902  ldc.i4.2
0x1903  callvirt instance string [mscorlib]System.String::Substring(int32)
0x1908  ldstr    asc_55E6// "\\"
0x190d  ldc.i4.4
0x190e  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x1913  brfalse.s loc_193F
0x1915  ldarg.0
0x1916  ldc.i4.2
0x1917  callvirt instance string [mscorlib]System.String::Substring(int32)
0x191c  ldstr    asc_55E6// "\\"
0x1921  ldc.i4.4
0x1922  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x1927  ldc.i4.m1
0x1928  beq.s    loc_193F
0x192a  ldarg.0
0x192b  ldc.i4.2
0x192c  callvirt instance string [mscorlib]System.String::Substring(int32)
0x1931  ldstr    asc_55E0// "\\\\"
0x1936  ldc.i4.4
0x1937  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x193c  ldc.i4.m1
0x193d  beq.s    loc_1941
0x193f  ldc.i4.0
0x1940  ret
0x1941  ldc.i4.1
0x1942  ret
0x1943  ldc.i4.0
0x1944  ret
```
