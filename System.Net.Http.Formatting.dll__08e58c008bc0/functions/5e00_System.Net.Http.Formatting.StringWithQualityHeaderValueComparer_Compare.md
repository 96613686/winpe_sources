# System.Net.Http.Formatting.StringWithQualityHeaderValueComparer::Compare

- ea: `0x5e00`
- end: `0x5ea4`
- name: `System.Net.Http.Formatting.StringWithQualityHeaderValueComparer::Compare`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x5e00`

## pseudocode

```c

```

## disassembly

```asm
0x5e00  ldarg.1
0x5e01  callvirt instance valuetype [mscorlib]System.Nullable`1<float64> [System.Net.Http]System.Net.Http.Headers.StringWithQualityHeaderValue::get_Quality()
0x5e06  stloc.2
0x5e07  ldloca.s 2
0x5e09  call     instance bool valuetype [mscorlib]System.Nullable`1<float64>::get_HasValue()
0x5e0e  brtrue.s loc_5E1B
0x5e10  ldc.r8   1.0
0x5e19  br.s     loc_5E22
0x5e1b  ldloca.s 2
0x5e1d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<float64>::GetValueOrDefault()
0x5e22  ldarg.2
0x5e23  callvirt instance valuetype [mscorlib]System.Nullable`1<float64> [System.Net.Http]System.Net.Http.Headers.StringWithQualityHeaderValue::get_Quality()
0x5e28  stloc.2
0x5e29  ldloca.s 2
0x5e2b  call     instance bool valuetype [mscorlib]System.Nullable`1<float64>::get_HasValue()
0x5e30  brtrue.s loc_5E3D
0x5e32  ldc.r8   1.0
0x5e3b  br.s     loc_5E44
0x5e3d  ldloca.s 2
0x5e3f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<float64>::GetValueOrDefault()
0x5e44  stloc.0
0x5e45  ldloc.0
0x5e46  sub
0x5e47  stloc.1
0x5e48  ldloc.1
0x5e49  ldc.r8   0.0
0x5e52  bge.un.s loc_5E56
0x5e54  ldc.i4.m1
0x5e55  ret
0x5e56  ldloc.1
0x5e57  ldc.r8   0.0
0x5e60  ble.un.s loc_5E64
0x5e62  ldc.i4.1
0x5e63  ret
0x5e64  ldarg.1
0x5e65  callvirt instance string [System.Net.Http]System.Net.Http.Headers.StringWithQualityHeaderValue::get_Value()
0x5e6a  ldarg.2
0x5e6b  callvirt instance string [System.Net.Http]System.Net.Http.Headers.StringWithQualityHeaderValue::get_Value()
0x5e70  ldc.i4.5
0x5e71  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x5e76  brtrue.s loc_5EA2
0x5e78  ldarg.1
0x5e79  callvirt instance string [System.Net.Http]System.Net.Http.Headers.StringWithQualityHeaderValue::get_Value()
0x5e7e  ldstr    asc_10C2C// "*"
0x5e83  ldc.i4.5
0x5e84  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x5e89  brfalse.s loc_5E8D
0x5e8b  ldc.i4.m1
0x5e8c  ret
0x5e8d  ldarg.2
0x5e8e  callvirt instance string [System.Net.Http]System.Net.Http.Headers.StringWithQualityHeaderValue::get_Value()
0x5e93  ldstr    asc_10C2C// "*"
0x5e98  ldc.i4.5
0x5e99  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x5e9e  brfalse.s loc_5EA2
0x5ea0  ldc.i4.1
0x5ea1  ret
0x5ea2  ldc.i4.0
0x5ea3  ret
```
