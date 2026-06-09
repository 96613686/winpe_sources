# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::IsOnDefinitionPath

- ea: `0x22c0`
- end: `0x22f1`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::IsOnDefinitionPath`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d70`
- `0x1e90`

## callees

- `0x22c0`

## pseudocode

```c

```

## disassembly

```asm
0x22c0  ldarg.1
0x22c1  ldarg.0
0x22c2  ldc.i4.4
0x22c3  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22c8  brfalse.s loc_22EF
0x22ca  ldarg.1
0x22cb  callvirt instance int32 [mscorlib]System.String::get_Length()
0x22d0  ldarg.0
0x22d1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x22d6  ble.s    loc_22ED
0x22d8  ldarg.1
0x22d9  ldarg.0
0x22da  callvirt instance int32 [mscorlib]System.String::get_Length()
0x22df  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x22e4  call     bool [mscorlib]System.Char::IsDigit(char)
0x22e9  brtrue.s loc_22EF
0x22eb  ldc.i4.1
0x22ec  ret
0x22ed  ldc.i4.1
0x22ee  ret
0x22ef  ldc.i4.0
0x22f0  ret
```
