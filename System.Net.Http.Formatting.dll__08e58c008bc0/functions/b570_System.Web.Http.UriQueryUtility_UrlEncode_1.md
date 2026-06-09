# System.Web.Http.UriQueryUtility::UrlEncode_1

- ea: `0xb570`
- end: `0xb638`
- name: `System.Web.Http.UriQueryUtility::UrlEncode_1`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xb540`

## callees

- `0xb570`
- `0xb730`
- `0xb750`
- `0xb7b0`

## pseudocode

```c

```

## disassembly

```asm
0xb570  ldarg.0
0xb571  ldarg.1
0xb572  ldarg.2
0xb573  call     bool System.Web.Http.UriQueryUtility::ValidateUrlEncodingParameters(unsigned int8[] bytes, int32 offset, int32 count)
0xb578  brtrue.s loc_B57C
0xb57a  ldnull
0xb57b  ret
0xb57c  ldc.i4.0
0xb57d  stloc.0
0xb57e  ldc.i4.0
0xb57f  stloc.1
0xb580  ldc.i4.0
0xb581  stloc.s  4
0xb583  br.s     loc_B5AC
0xb585  ldarg.0
0xb586  ldarg.1
0xb587  ldloc.s  4
0xb589  add
0xb58a  ldelem.u1
0xb58b  stloc.s  5
0xb58d  ldloc.s  5
0xb58f  ldc.i4.s 0x20
0xb591  bne.un.s loc_B599
0xb593  ldloc.0
0xb594  ldc.i4.1
0xb595  add
0xb596  stloc.0
0xb597  br.s     loc_B5A6
0xb599  ldloc.s  5
0xb59b  call     bool System.Web.Http.UriQueryUtility::IsUrlSafeChar(char ch)
0xb5a0  brtrue.s loc_B5A6
0xb5a2  ldloc.1
0xb5a3  ldc.i4.1
0xb5a4  add
0xb5a5  stloc.1
0xb5a6  ldloc.s  4
0xb5a8  ldc.i4.1
0xb5a9  add
0xb5aa  stloc.s  4
0xb5ac  ldloc.s  4
0xb5ae  ldarg.2
0xb5af  blt.s    loc_B585
0xb5b1  ldloc.0
0xb5b2  brtrue.s loc_B5B9
0xb5b4  ldloc.1
0xb5b5  brtrue.s loc_B5B9
0xb5b7  ldarg.0
0xb5b8  ret
0xb5b9  ldarg.2
0xb5ba  ldloc.1
0xb5bb  ldc.i4.2
0xb5bc  mul
0xb5bd  add
0xb5be  newarr   [mscorlib]System.Byte
0xb5c3  stloc.2
0xb5c4  ldc.i4.0
0xb5c5  stloc.3
0xb5c6  ldc.i4.0
0xb5c7  stloc.s  6
0xb5c9  br.s     loc_B631
0xb5cb  ldarg.0
0xb5cc  ldarg.1
0xb5cd  ldloc.s  6
0xb5cf  add
0xb5d0  ldelem.u1
0xb5d1  stloc.s  7
0xb5d3  ldloc.s  7
0xb5d5  stloc.s  8
0xb5d7  ldloc.s  8
0xb5d9  call     bool System.Web.Http.UriQueryUtility::IsUrlSafeChar(char ch)
0xb5de  brfalse.s loc_B5EB
0xb5e0  ldloc.2
0xb5e1  ldloc.3
0xb5e2  dup
0xb5e3  ldc.i4.1
0xb5e4  add
0xb5e5  stloc.3
0xb5e6  ldloc.s  7
0xb5e8  stelem.i1
0xb5e9  br.s     loc_B62B
0xb5eb  ldloc.s  8
0xb5ed  ldc.i4.s 0x20
0xb5ef  bne.un.s loc_B5FC
0xb5f1  ldloc.2
0xb5f2  ldloc.3
0xb5f3  dup
0xb5f4  ldc.i4.1
0xb5f5  add
0xb5f6  stloc.3
0xb5f7  ldc.i4.s 0x2B
0xb5f9  stelem.i1
0xb5fa  br.s     loc_B62B
0xb5fc  ldloc.2
0xb5fd  ldloc.3
0xb5fe  dup
0xb5ff  ldc.i4.1
0xb600  add
0xb601  stloc.3
0xb602  ldc.i4.s 0x25
0xb604  stelem.i1
0xb605  ldloc.2
0xb606  ldloc.3
0xb607  dup
0xb608  ldc.i4.1
0xb609  add
0xb60a  stloc.3
0xb60b  ldloc.s  7
0xb60d  ldc.i4.4
0xb60e  shr
0xb60f  ldc.i4.s 0xF
0xb611  and
0xb612  call     char System.Web.Http.UriQueryUtility::IntToHex(int32 n)
0xb617  conv.u1
0xb618  stelem.i1
0xb619  ldloc.2
0xb61a  ldloc.3
0xb61b  dup
0xb61c  ldc.i4.1
0xb61d  add
0xb61e  stloc.3
0xb61f  ldloc.s  7
0xb621  ldc.i4.s 0xF
0xb623  and
0xb624  call     char System.Web.Http.UriQueryUtility::IntToHex(int32 n)
0xb629  conv.u1
0xb62a  stelem.i1
0xb62b  ldloc.s  6
0xb62d  ldc.i4.1
0xb62e  add
0xb62f  stloc.s  6
0xb631  ldloc.s  6
0xb633  ldarg.2
0xb634  blt.s    loc_B5CB
0xb636  ldloc.2
0xb637  ret
```
