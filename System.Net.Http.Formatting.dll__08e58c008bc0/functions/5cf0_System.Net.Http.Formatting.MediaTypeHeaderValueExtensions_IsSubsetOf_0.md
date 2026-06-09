# System.Net.Http.Formatting.MediaTypeHeaderValueExtensions::IsSubsetOf_0

- ea: `0x5cf0`
- end: `0x5dc1`
- name: `System.Net.Http.Formatting.MediaTypeHeaderValueExtensions::IsSubsetOf_0`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x5ce0`
- `0x7170`

## callees

- `0x5cf0`
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
0x5cf0  ldarg.1
0x5cf1  brtrue.s loc_5CF8
0x5cf3  ldarg.2
0x5cf4  ldc.i4.0
0x5cf5  stind.i4
0x5cf6  ldc.i4.0
0x5cf7  ret
0x5cf8  ldloca.s 0
0x5cfa  ldarg.0
0x5cfb  call     instance void System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::.ctor(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaTypeHeaderValue)
0x5d00  ldloca.s 1
0x5d02  ldarg.1
0x5d03  call     instance void System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::.ctor(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue mediaTypeHeaderValue)
0x5d08  ldarg.2
0x5d09  ldloca.s 1
0x5d0b  call     instance bool System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::get_IsAllMediaRange()
0x5d10  brtrue.s loc_5D21
0x5d12  ldloca.s 1
0x5d14  call     instance bool System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::get_IsSubtypeMediaRange()
0x5d19  brtrue.s loc_5D1E
0x5d1b  ldc.i4.0
0x5d1c  br.s     loc_5D22
0x5d1e  ldc.i4.1
0x5d1f  br.s     loc_5D22
0x5d21  ldc.i4.2
0x5d22  stind.i4
0x5d23  ldloca.s 0
0x5d25  ldloca.s 1
0x5d27  call     instance bool System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::TypesEqual(valuetype System.Net.Http.Formatting.ParsedMediaTypeHeaderValue& other)
0x5d2c  brtrue.s loc_5D35
0x5d2e  ldarg.2
0x5d2f  ldind.i4
0x5d30  ldc.i4.2
0x5d31  beq.s    loc_5D47
0x5d33  ldc.i4.0
0x5d34  ret
0x5d35  ldloca.s 0
0x5d37  ldloca.s 1
0x5d39  call     instance bool System.Net.Http.Formatting.ParsedMediaTypeHeaderValue::SubTypesEqual(valuetype System.Net.Http.Formatting.ParsedMediaTypeHeaderValue& other)
0x5d3e  brtrue.s loc_5D47
0x5d40  ldarg.2
0x5d41  ldind.i4
0x5d42  ldc.i4.1
0x5d43  beq.s    loc_5D47
0x5d45  ldc.i4.0
0x5d46  ret
0x5d47  ldarg.0
0x5d48  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [System.Net.Http]System.Net.Http.Headers.NameValueHeaderValue> [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::get_Parameters()
0x5d4d  call     T0x2B000043
0x5d52  stloc.2
0x5d53  ldloc.2
0x5d54  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.NameValueHeaderValue>::get_Count()
0x5d59  stloc.3
0x5d5a  ldarg.1
0x5d5b  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class [System.Net.Http]System.Net.Http.Headers.NameValueHeaderValue> [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::get_Parameters()
0x5d60  call     T0x2B000043
0x5d65  stloc.s  4
0x5d67  ldloc.s  4
0x5d69  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.NameValueHeaderValue>::get_Count()
0x5d6e  stloc.s  5
0x5d70  ldc.i4.0
0x5d71  stloc.s  6
0x5d73  br.s     loc_5DBA
0x5d75  ldloc.2
0x5d76  ldloc.s  6
0x5d78  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.NameValueHeaderValue>::get_Item(!!T0)
0x5d7d  stloc.s  7
0x5d7f  ldc.i4.0
0x5d80  stloc.s  8
0x5d82  ldc.i4.0
0x5d83  stloc.s  9
0x5d85  br.s     loc_5DA8
0x5d87  ldloc.s  4
0x5d89  ldloc.s  9
0x5d8b  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http]System.Net.Http.Headers.NameValueHeaderValue>::get_Item(!!T0)
0x5d90  stloc.s  0xA
0x5d92  ldloc.s  7
0x5d94  ldloc.s  0xA
0x5d96  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x5d9b  brfalse.s loc_5DA2
0x5d9d  ldc.i4.1
0x5d9e  stloc.s  8
0x5da0  br.s     loc_5DAE
0x5da2  ldloc.s  9
0x5da4  ldc.i4.1
0x5da5  add
0x5da6  stloc.s  9
0x5da8  ldloc.s  9
0x5daa  ldloc.s  5
0x5dac  blt.s    loc_5D87
0x5dae  ldloc.s  8
0x5db0  brtrue.s loc_5DB4
0x5db2  ldc.i4.0
0x5db3  ret
0x5db4  ldloc.s  6
0x5db6  ldc.i4.1
0x5db7  add
0x5db8  stloc.s  6
0x5dba  ldloc.s  6
0x5dbc  ldloc.3
0x5dbd  blt.s    loc_5D75
0x5dbf  ldc.i4.1
0x5dc0  ret
```
