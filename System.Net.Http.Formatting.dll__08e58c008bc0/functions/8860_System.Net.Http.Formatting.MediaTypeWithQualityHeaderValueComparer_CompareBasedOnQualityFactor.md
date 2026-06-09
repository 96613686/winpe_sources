# System.Net.Http.Formatting.MediaTypeWithQualityHeaderValueComparer::CompareBasedOnQualityFactor

- ea: `0x8860`
- end: `0x88c6`
- name: `System.Net.Http.Formatting.MediaTypeWithQualityHeaderValueComparer::CompareBasedOnQualityFactor`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x87d0`

## callees

- `0x8860`

## pseudocode

```c

```

## disassembly

```asm
0x8860  ldarg.0
0x8861  callvirt instance valuetype [mscorlib]System.Nullable`1<float64> [System.Net.Http]System.Net.Http.Headers.MediaTypeWithQualityHeaderValue::get_Quality()
0x8866  stloc.2
0x8867  ldloca.s 2
0x8869  call     instance bool valuetype [mscorlib]System.Nullable`1<float64>::get_HasValue()
0x886e  brtrue.s loc_887B
0x8870  ldc.r8   1.0
0x8879  br.s     loc_8882
0x887b  ldloca.s 2
0x887d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<float64>::GetValueOrDefault()
0x8882  ldarg.1
0x8883  callvirt instance valuetype [mscorlib]System.Nullable`1<float64> [System.Net.Http]System.Net.Http.Headers.MediaTypeWithQualityHeaderValue::get_Quality()
0x8888  stloc.2
0x8889  ldloca.s 2
0x888b  call     instance bool valuetype [mscorlib]System.Nullable`1<float64>::get_HasValue()
0x8890  brtrue.s loc_889D
0x8892  ldc.r8   1.0
0x889b  br.s     loc_88A4
0x889d  ldloca.s 2
0x889f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<float64>::GetValueOrDefault()
0x88a4  stloc.0
0x88a5  ldloc.0
0x88a6  sub
0x88a7  stloc.1
0x88a8  ldloc.1
0x88a9  ldc.r8   0.0
0x88b2  bge.un.s loc_88B6
0x88b4  ldc.i4.m1
0x88b5  ret
0x88b6  ldloc.1
0x88b7  ldc.r8   0.0
0x88c0  ble.un.s loc_88C4
0x88c2  ldc.i4.1
0x88c3  ret
0x88c4  ldc.i4.0
0x88c5  ret
```
