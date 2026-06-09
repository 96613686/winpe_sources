# std::tr1::_Compare<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort const *,std::tr1::regex_traits<ushort>>(std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort const *,ushort const *,std::tr1::regex_traits<ushort> const &,std::tr1::regex_constants::syntax_option_type,bool)

- ea: `0x1800118f4`
- end: `0x180011a15`
- name: `??$_Compare@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGV?$regex_traits@G@tr1@2@@tr1@std@@YA?AV?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V21@0PEBG1AEBV?$regex_traits@G@01@W4syntax_option_type@regex_constants@01@_N@Z`
- size: `289`
- prototype: `unsigned __int16 **__fastcall(unsigned __int16 **, unsigned __int16 *, unsigned __int16 *, _WORD *, _WORD *, __int64, __int16, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010fe8`

## callees

- `0x1800118f4`
- `0x180017a38`
- `0x180017a80`

## pseudocode

```c
unsigned __int16 **__fastcall std::tr1::_Compare<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,unsigned short const *,std::tr1::regex_traits<unsigned short>>(
        unsigned __int16 **a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _WORD *a4,
        _WORD *a5,
        __int64 a6,
        __int16 a7,
        char a8)
{
  bool v8; // zf
  unsigned __int16 *v11; // rbx
  unsigned __int16 *v13; // r14
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rcx
  __int64 v17; // [rsp+40h] [rbp+8h] BYREF

  v8 = (a7 & 0x800) == 0;
  *a1 = a3;
  v11 = a2;
  if ( !v8 )
  {
    v13 = a2;
    v17 = a6;
    v14 = a2;
    while ( v13 != a3 )
    {
      if ( a4 == a5 )
        goto LABEL_8;
      if ( !(unsigned __int8)std::tr1::_Cmp_collate<std::tr1::regex_traits<unsigned short>>::operator()(
                               &v17,
                               *v13,
                               (unsigned __int16)*a4) )
        goto LABEL_24;
      ++a4;
      v14 = ++v13;
    }
    goto LABEL_7;
  }
  if ( (a7 & 0x100) != 0 )
  {
    v13 = a2;
    v17 = a6;
    v14 = a2;
    while ( v13 != a3 )
    {
      if ( a4 == a5 )
        goto LABEL_8;
      if ( !(unsigned __int8)std::tr1::_Cmp_icase<std::tr1::regex_traits<unsigned short>>::operator()(
                               &v17,
                               *v13,
                               (unsigned __int16)*a4) )
        goto LABEL_24;
      ++a4;
      v14 = ++v13;
    }
LABEL_7:
    if ( a4 == a5 )
    {
LABEL_8:
      v11 = v13;
    }
    else
    {
LABEL_22:
      if ( a8 )
        v11 = v14;
    }
    goto LABEL_24;
  }
  v15 = a2;
  v14 = a2;
  while ( v15 != a3 )
  {
    if ( a4 == a5 )
      goto LABEL_21;
    if ( *v15 != *a4 )
      goto LABEL_24;
    ++a4;
    v14 = ++v15;
  }
  if ( a4 != a5 )
    goto LABEL_22;
LABEL_21:
  v11 = v15;
LABEL_24:
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x1800118f4  mov     [rsp+arg_8], rbx
0x1800118f9  mov     [rsp+arg_10], rsi
0x1800118fe  push    rdi
0x1800118ff  push    r14
0x180011901  push    r15
0x180011903  sub     rsp, 20h
0x180011907  test    dword ptr [rsp+38h+arg_30], 800h
0x18001190f  mov     rsi, r9
0x180011912  mov     rdi, r8
0x180011915  mov     [rcx], r8
0x180011918  mov     rbx, rdx
0x18001191b  mov     r15, rcx
0x18001191e  jz      short loc_180011976
0x180011920  mov     rax, [rsp+38h+arg_28]
0x180011925  mov     r14, rdx
0x180011928  mov     [rsp+38h+arg_0], rax
0x18001192d  mov     rax, rdx
0x180011930  cmp     r14, rdi
0x180011933  jz      short loc_180011963
0x180011935  cmp     rsi, [rsp+38h+arg_20]
0x18001193a  jz      short loc_18001196E
0x18001193c  movzx   r8d, word ptr [rsi]
0x180011940  lea     rcx, [rsp+38h+arg_0]
0x180011945  movzx   edx, word ptr [r14]
0x180011949  call    ??R?$_Cmp_collate@V?$regex_traits@G@tr1@std@@@tr1@std@@QEAA_NGG@Z; std::tr1::_Cmp_collate<std::tr1::regex_traits<ushort>>::operator()(ushort,ushort)
0x18001194e  test    al, al
0x180011950  jz      loc_1800119FB
0x180011956  add     rsi, 2
0x18001195a  add     r14, 2
0x18001195e  mov     rax, r14
0x180011961  jmp     short loc_180011930
0x180011963  cmp     rsi, [rsp+38h+arg_20]
0x180011968  jnz     loc_1800119F2
0x18001196e  mov     rbx, r14
0x180011971  jmp     loc_1800119FB
0x180011976  test    dword ptr [rsp+38h+arg_30], 100h
0x18001197e  jz      short loc_1800119BF
0x180011980  mov     rax, [rsp+38h+arg_28]
0x180011985  mov     r14, rbx
0x180011988  mov     [rsp+38h+arg_0], rax
0x18001198d  mov     rax, rbx
0x180011990  cmp     r14, rdi
0x180011993  jz      short loc_180011963
0x180011995  cmp     rsi, [rsp+38h+arg_20]
0x18001199a  jz      short loc_18001196E
0x18001199c  movzx   r8d, word ptr [rsi]
0x1800119a0  lea     rcx, [rsp+38h+arg_0]
0x1800119a5  movzx   edx, word ptr [r14]
0x1800119a9  call    ??R?$_Cmp_icase@V?$regex_traits@G@tr1@std@@@tr1@std@@QEAA_NGG@Z; std::tr1::_Cmp_icase<std::tr1::regex_traits<ushort>>::operator()(ushort,ushort)
0x1800119ae  test    al, al
0x1800119b0  jz      short loc_1800119FB
0x1800119b2  add     rsi, 2
0x1800119b6  add     r14, 2
0x1800119ba  mov     rax, r14
0x1800119bd  jmp     short loc_180011990
0x1800119bf  mov     rcx, rbx
0x1800119c2  mov     rax, rbx
0x1800119c5  cmp     rcx, rdi
0x1800119c8  jz      short loc_1800119E6
0x1800119ca  cmp     rsi, [rsp+38h+arg_20]
0x1800119cf  jz      short loc_1800119ED
0x1800119d1  movzx   eax, word ptr [rsi]
0x1800119d4  cmp     [rcx], ax
0x1800119d7  jnz     short loc_1800119FB
0x1800119d9  add     rsi, 2
0x1800119dd  add     rcx, 2
0x1800119e1  mov     rax, rcx
0x1800119e4  jmp     short loc_1800119C5
0x1800119e6  cmp     rsi, [rsp+38h+arg_20]
0x1800119eb  jnz     short loc_1800119F2
0x1800119ed  mov     rbx, rcx
0x1800119f0  jmp     short loc_1800119FB
0x1800119f2  cmp     [rsp+38h+arg_38], 0
0x1800119f7  cmovnz  rbx, rax
0x1800119fb  mov     [r15], rbx
0x1800119fe  mov     rax, r15
0x180011a01  mov     rbx, [rsp+38h+arg_8]
0x180011a06  mov     rsi, [rsp+38h+arg_10]
0x180011a0b  add     rsp, 20h
0x180011a0f  pop     r15
0x180011a11  pop     r14
0x180011a13  pop     rdi
0x180011a14  retn
```
