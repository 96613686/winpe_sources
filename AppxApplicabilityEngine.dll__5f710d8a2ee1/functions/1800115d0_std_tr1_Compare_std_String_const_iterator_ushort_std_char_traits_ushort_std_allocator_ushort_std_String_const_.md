# std::tr1::_Compare<std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::tr1::regex_traits<ushort>>(std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_String_const_iterator<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::tr1::regex_traits<ushort> const &,std::tr1::regex_constants::syntax_option_type,bool)

- ea: `0x1800115d0`
- end: `0x18001170e`
- name: `??$_Compare@V?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$regex_traits@G@tr1@2@@tr1@std@@YA?AV?$_String_const_iterator@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V21@000AEBV?$regex_traits@G@01@W4syntax_option_type@regex_constants@01@_N@Z`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010fe8`

## callees

- `0x1800115d0`
- `0x180017a38`
- `0x180017a80`

## pseudocode

```c
unsigned __int16 **__fastcall std::tr1::_Compare<std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,std::_String_const_iterator<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>,std::tr1::regex_traits<unsigned short>>(
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
  if ( v8 )
  {
    if ( (a7 & 0x100) == 0 )
    {
      v14 = a2;
      v15 = a2;
      while ( v14 != a3 )
      {
        if ( a4 == a5 )
          goto LABEL_8;
        if ( *v15 != *a4 )
          goto LABEL_27;
        v14 = v15 + 1;
        ++a4;
        ++v15;
      }
      if ( a4 == a5 )
        goto LABEL_8;
      if ( a8 && v15 == a3 )
        v11 = v15;
      goto LABEL_27;
    }
    v13 = a2;
    v17 = a6;
    v14 = a2;
    while ( v14 != a3 )
    {
      if ( a4 == a5 )
        goto LABEL_8;
      if ( !(unsigned __int8)std::tr1::_Cmp_icase<std::tr1::regex_traits<unsigned short>>::operator()(
                               &v17,
                               *v13,
                               (unsigned __int16)*a4) )
        goto LABEL_27;
      v14 = v13 + 1;
      ++a4;
      ++v13;
    }
  }
  else
  {
    v13 = a2;
    v17 = a6;
    v14 = a2;
    while ( v14 != a3 )
    {
      if ( a4 == a5 )
        goto LABEL_8;
      if ( !(unsigned __int8)std::tr1::_Cmp_collate<std::tr1::regex_traits<unsigned short>>::operator()(
                               &v17,
                               *v13,
                               (unsigned __int16)*a4) )
        goto LABEL_27;
      v14 = v13 + 1;
      ++a4;
      ++v13;
    }
  }
  if ( a4 == a5 )
  {
LABEL_8:
    v11 = v14;
    goto LABEL_27;
  }
  if ( a8 && v13 == a3 )
    v11 = v13;
LABEL_27:
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x1800115d0  mov     [rsp+arg_8], rbx
0x1800115d5  mov     [rsp+arg_10], rsi
0x1800115da  push    rdi
0x1800115db  push    r14
0x1800115dd  push    r15
0x1800115df  sub     rsp, 20h
0x1800115e3  test    dword ptr [rsp+38h+arg_30], 800h
0x1800115eb  mov     rdi, r9
0x1800115ee  mov     rsi, r8
0x1800115f1  mov     [rcx], r8
0x1800115f4  mov     rbx, rdx
0x1800115f7  mov     r15, rcx
0x1800115fa  jz      short loc_18001166A
0x1800115fc  mov     rax, [rsp+38h+arg_28]
0x180011601  mov     r14, rdx
0x180011604  mov     [rsp+38h+arg_0], rax
0x180011609  mov     rax, rdx
0x18001160c  cmp     rax, rsi
0x18001160f  jz      short loc_18001163F
0x180011611  cmp     rdi, [rsp+38h+arg_20]
0x180011616  jz      short loc_180011646
0x180011618  movzx   r8d, word ptr [rdi]
0x18001161c  lea     rcx, [rsp+38h+arg_0]
0x180011621  movzx   edx, word ptr [r14]
0x180011625  call    ??R?$_Cmp_collate@V?$regex_traits@G@tr1@std@@@tr1@std@@QEAA_NGG@Z; std::tr1::_Cmp_collate<std::tr1::regex_traits<ushort>>::operator()(ushort,ushort)
0x18001162a  test    al, al
0x18001162c  jz      loc_1800116F4
0x180011632  lea     rax, [r14+2]
0x180011636  add     rdi, 2
0x18001163a  mov     r14, rax
0x18001163d  jmp     short loc_18001160C
0x18001163f  cmp     rdi, [rsp+38h+arg_20]
0x180011644  jnz     short loc_18001164E
0x180011646  mov     rbx, rax
0x180011649  jmp     loc_1800116F4
0x18001164e  cmp     [rsp+38h+arg_38], 0
0x180011653  jz      loc_1800116F4
0x180011659  cmp     r14, rsi
0x18001165c  jnz     loc_1800116F4
0x180011662  mov     rbx, r14
0x180011665  jmp     loc_1800116F4
0x18001166a  test    dword ptr [rsp+38h+arg_30], 100h
0x180011672  jz      short loc_1800116B3
0x180011674  mov     rax, [rsp+38h+arg_28]
0x180011679  mov     r14, rdx
0x18001167c  mov     [rsp+38h+arg_0], rax
0x180011681  mov     rax, rdx
0x180011684  cmp     rax, rsi
0x180011687  jz      short loc_18001163F
0x180011689  cmp     rdi, [rsp+38h+arg_20]
0x18001168e  jz      short loc_180011646
0x180011690  movzx   r8d, word ptr [rdi]
0x180011694  lea     rcx, [rsp+38h+arg_0]
0x180011699  movzx   edx, word ptr [r14]
0x18001169d  call    ??R?$_Cmp_icase@V?$regex_traits@G@tr1@std@@@tr1@std@@QEAA_NGG@Z; std::tr1::_Cmp_icase<std::tr1::regex_traits<ushort>>::operator()(ushort,ushort)
0x1800116a2  test    al, al
0x1800116a4  jz      short loc_1800116F4
0x1800116a6  lea     rax, [r14+2]
0x1800116aa  add     rdi, 2
0x1800116ae  mov     r14, rax
0x1800116b1  jmp     short loc_180011684
0x1800116b3  mov     rax, rdx
0x1800116b6  mov     rcx, rdx
0x1800116b9  cmp     rax, rsi
0x1800116bc  jz      short loc_1800116DA
0x1800116be  cmp     rdi, [rsp+38h+arg_20]
0x1800116c3  jz      short loc_180011646
0x1800116c5  movzx   eax, word ptr [rdi]
0x1800116c8  cmp     [rcx], ax
0x1800116cb  jnz     short loc_1800116F4
0x1800116cd  lea     rax, [rcx+2]
0x1800116d1  add     rdi, 2
0x1800116d5  mov     rcx, rax
0x1800116d8  jmp     short loc_1800116B9
0x1800116da  cmp     rdi, [rsp+38h+arg_20]
0x1800116df  jz      loc_180011646
0x1800116e5  cmp     [rsp+38h+arg_38], 0
0x1800116ea  jz      short loc_1800116F4
0x1800116ec  cmp     rcx, rsi
0x1800116ef  jnz     short loc_1800116F4
0x1800116f1  mov     rbx, rcx
0x1800116f4  mov     [r15], rbx
0x1800116f7  mov     rax, r15
0x1800116fa  mov     rbx, [rsp+38h+arg_8]
0x1800116ff  mov     rsi, [rsp+38h+arg_10]
0x180011704  add     rsp, 20h
0x180011708  pop     r15
0x18001170a  pop     r14
0x18001170c  pop     rdi
0x18001170d  retn
```
