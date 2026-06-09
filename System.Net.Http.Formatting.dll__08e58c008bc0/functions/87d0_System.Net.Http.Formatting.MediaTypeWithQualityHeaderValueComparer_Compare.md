# System.Net.Http.Formatting.MediaTypeWithQualityHeaderValueComparer::Compare

- ea: `0x87d0`
- end: `0x885d`
- name: `System.Net.Http.Formatting.MediaTypeWithQualityHeaderValueComparer::Compare`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x87d0`
- `0x8860`
- `0x8980`
- `0x89f0`
- `0x8a00`
- `0x8a10`
- `0x8a40`

## pseudocode

```c

```

## disassembly

```asm
0x87d0  ldarg.1
0x87d1  ldarg.2
0x87d2  bne.un.s loc_87D6
0x87d4  ldc.i4.0
0x87d5  ret
0x87d6  ldarg.1
0x87d7  ldarg.2
0x87d8  call     int32 System.Net.Http.Formatting.MediaTypeWithQualityHeaderValueComparer::CompareBasedOnQualityFactor(class [System.Net.Http]System.Net.Http.Headers.MediaTypeWithQualityHeaderValue mediaType1, class [System.Net.Http]System.Net.Http.Headers.MediaTypeWithQualityHeaderValue mediaType2)
0x87dd  stloc.0
0x87de  ldloc.0
0x87df  brtrue.s loc_885B
0x87e1  ldloca.s 1
0x87e3  ldarg.1
0x87e4  call     instance void System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::.ctor(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaTypeHeaderValue)
0x87e9  ldloca.s 2
0x87eb  ldarg.2
0x87ec  call     instance void System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::.ctor(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaTypeHeaderValue)
0x87f1  ldloca.s 1
0x87f3  ldloca.s 2
0x87f5  call     instance bool System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::TypesEqual(valuetype System.Net.Http.Formatting.ParsedMediaTypeHeaderValue& other)
0x87fa  brtrue.s loc_883A
0x87fc  ldloca.s 1
0x87fe  call     instance bool System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::get_IsAllMediaRange()
0x8803  brfalse.s loc_8807
0x8805  ldc.i4.m1
0x8806  ret
0x8807  ldloca.s 2
0x8809  call     instance bool System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::get_IsAllMediaRange()
0x880e  brfalse.s loc_8812
0x8810  ldc.i4.1
0x8811  ret
0x8812  ldloca.s 1
0x8814  call     instance bool System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::get_IsSubtypeMediaRange()
0x8819  brfalse.s loc_8826
0x881b  ldloca.s 2
0x881d  call     instance bool System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::get_IsSubtypeMediaRange()
0x8822  brtrue.s loc_8826
0x8824  ldc.i4.m1
0x8825  ret
0x8826  ldloca.s 1
0x8828  call     instance bool System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::get_IsSubtypeMediaRange()
0x882d  brtrue.s loc_885B
0x882f  ldloca.s 2
0x8831  call     instance bool System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::get_IsSubtypeMediaRange()
0x8836  brfalse.s loc_885B
0x8838  ldc.i4.1
0x8839  ret
0x883a  ldloca.s 1
0x883c  ldloca.s 2
0x883e  call     instance bool System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::SubTypesEqual(valuetype System.Net.Http.Formatting.ParsedMediaTypeHeaderValue& other)
0x8843  brtrue.s loc_885B
0x8845  ldloca.s 1
0x8847  call     instance bool System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::get_IsSubtypeMediaRange()
0x884c  brfalse.s loc_8850
0x884e  ldc.i4.m1
0x884f  ret
0x8850  ldloca.s 2
0x8852  call     instance bool System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::get_IsSubtypeMediaRange()
0x8857  brfalse.s loc_885B
0x8859  ldc.i4.1
0x885a  ret
0x885b  ldloc.0
0x885c  ret
```
