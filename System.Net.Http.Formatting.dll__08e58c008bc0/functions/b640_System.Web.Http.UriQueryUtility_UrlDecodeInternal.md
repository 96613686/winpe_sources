# System.Web.Http.UriQueryUtility::UrlDecodeInternal

- ea: `0xb640`
- end: `0xb6e3`
- name: `System.Web.Http.UriQueryUtility::UrlDecodeInternal`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xb520`

## callees

- `0xb640`
- `0xb6f0`
- `0xe450`
- `0xe480`
- `0xe4b0`
- `0xe4f0`

## pseudocode

```c

```

## disassembly

```asm
0xb640  ldarg.0
0xb641  brtrue.s loc_B645
0xb643  ldnull
0xb644  ret
0xb645  ldarg.0
0xb646  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb64b  stloc.0
0xb64c  ldloc.0
0xb64d  ldarg.1
0xb64e  newobj   instance void UrlDecoder::.ctor(int32 bufferSize, class [mscorlib]System.Text.Encoding encoding)
0xb653  stloc.1
0xb654  ldc.i4.0
0xb655  stloc.2
0xb656  br.s     loc_B6D5
0xb658  ldarg.0
0xb659  ldloc.2
0xb65a  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xb65f  stloc.3
0xb660  ldloc.3
0xb661  ldc.i4.s 0x2B
0xb663  bne.un.s loc_B66A
0xb665  ldc.i4.s 0x20
0xb667  stloc.3
0xb668  br.s     loc_B6B7
0xb66a  ldloc.3
0xb66b  ldc.i4.s 0x25
0xb66d  bne.un.s loc_B6B7
0xb66f  ldloc.2
0xb670  ldloc.0
0xb671  ldc.i4.2
0xb672  sub
0xb673  bge.s    loc_B6B7
0xb675  ldarg.0
0xb676  ldloc.2
0xb677  ldc.i4.1
0xb678  add
0xb679  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xb67e  call     int32 System.Web.Http.UriQueryUtility::HexToInt(char h)
0xb683  stloc.s  4
0xb685  ldarg.0
0xb686  ldloc.2
0xb687  ldc.i4.2
0xb688  add
0xb689  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xb68e  call     int32 System.Web.Http.UriQueryUtility::HexToInt(char h)
0xb693  stloc.s  5
0xb695  ldloc.s  4
0xb697  ldc.i4.0
0xb698  blt.s    loc_B6B7
0xb69a  ldloc.s  5
0xb69c  ldc.i4.0
0xb69d  blt.s    loc_B6B7
0xb69f  ldloc.s  4
0xb6a1  ldc.i4.4
0xb6a2  shl
0xb6a3  ldloc.s  5
0xb6a5  or
0xb6a6  conv.u1
0xb6a7  stloc.s  6
0xb6a9  ldloc.2
0xb6aa  ldc.i4.2
0xb6ab  add
0xb6ac  stloc.2
0xb6ad  ldloc.1
0xb6ae  ldloc.s  6
0xb6b0  callvirt instance void UrlDecoder::AddByte(unsigned int8 b)
0xb6b5  br.s     loc_B6D1
0xb6b7  ldloc.3
0xb6b8  ldc.i4   0xFF80
0xb6bd  and
0xb6be  brtrue.s loc_B6CA
0xb6c0  ldloc.1
0xb6c1  ldloc.3
0xb6c2  conv.u1
0xb6c3  callvirt instance void UrlDecoder::AddByte(unsigned int8 b)
0xb6c8  br.s     loc_B6D1
0xb6ca  ldloc.1
0xb6cb  ldloc.3
0xb6cc  callvirt instance void UrlDecoder::AddChar(char ch)
0xb6d1  ldloc.2
0xb6d2  ldc.i4.1
0xb6d3  add
0xb6d4  stloc.2
0xb6d5  ldloc.2
0xb6d6  ldloc.0
0xb6d7  blt      loc_B658
0xb6dc  ldloc.1
0xb6dd  callvirt instance string UrlDecoder::GetString()
0xb6e2  ret
```
