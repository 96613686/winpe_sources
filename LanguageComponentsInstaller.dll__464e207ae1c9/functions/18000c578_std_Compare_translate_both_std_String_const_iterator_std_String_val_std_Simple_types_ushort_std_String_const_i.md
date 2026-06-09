# std::_Compare_translate_both<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::regex_traits<ushort>>(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::regex_traits<ushort> const &,std::regex_constants::syntax_option_type)

- ea: `0x18000c578`
- end: `0x18000c645`
- name: `??$_Compare_translate_both@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@V?$regex_traits@G@2@@std@@YA?AV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@000AEBV?$regex_traits@G@0@W4syntax_option_type@regex_constants@0@@Z`
- size: `205`
- prototype: `unsigned __int16 **__fastcall(unsigned __int16 **, unsigned __int16 *, unsigned __int16 *, _WORD *, _WORD *, __int64, __int16)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800208e4`

## callees

- `0x18000c578`

## import_xrefs

- `msvcp_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x18000c5c7`
- `msvcp_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x18000c5d8`
- `msvcp_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x18000c5c7`
- `msvcp_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x18000c5d8`

## pseudocode

```c
unsigned __int16 **__fastcall std::_Compare_translate_both<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::regex_traits<unsigned short>>(
        unsigned __int16 **a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _WORD *a4,
        _WORD *a5,
        __int64 a6,
        __int16 a7)
{
  unsigned __int16 *v9; // r15
  unsigned __int16 *i; // rdi
  unsigned __int16 v12; // r14
  __int16 v13; // bp
  unsigned __int16 *j; // rax
  unsigned __int16 **result; // rax

  v9 = a2;
  if ( (a7 & 0x100) != 0 )
  {
    for ( i = a2; i != a3; ++i )
    {
      if ( a4 == a5 )
        goto LABEL_8;
      v12 = *i;
      v13 = std::ctype<unsigned short>::tolower(*(_QWORD *)(a6 + 8), (unsigned __int16)*a4);
      if ( (unsigned __int16)std::ctype<unsigned short>::tolower(*(_QWORD *)(a6 + 8), v12) != v13 )
        goto LABEL_16;
      ++a4;
    }
    if ( a4 != a5 )
      goto LABEL_16;
LABEL_8:
    v9 = i;
  }
  else
  {
    for ( j = a2; j != a3; ++j )
    {
      if ( a4 == a5 )
        goto LABEL_15;
      if ( *j != *a4 )
        goto LABEL_16;
      ++a4;
    }
    if ( a4 != a5 )
      goto LABEL_16;
LABEL_15:
    v9 = j;
  }
LABEL_16:
  result = a1;
  *a1 = v9;
  return result;
}

```

## disassembly

```asm
0x18000c578  push    rbx
0x18000c57a  push    rbp
0x18000c57b  push    rsi
0x18000c57c  push    rdi
0x18000c57d  push    r12
0x18000c57f  push    r13
0x18000c581  push    r14
0x18000c583  push    r15
0x18000c585  sub     rsp, 28h
0x18000c589  test    [rsp+68h+arg_30], 100h
0x18000c594  mov     rbx, r9
0x18000c597  mov     rsi, r8
0x18000c59a  mov     r15, rdx
0x18000c59d  mov     r12, rcx
0x18000c5a0  jz      short loc_18000C5FC
0x18000c5a2  mov     r13, [rsp+68h+arg_28]
0x18000c5aa  mov     rdi, rdx
0x18000c5ad  cmp     rdi, rsi
0x18000c5b0  jz      short loc_18000C5ED
0x18000c5b2  cmp     rbx, [rsp+68h+arg_20]
0x18000c5ba  jz      short loc_18000C5F7
0x18000c5bc  movzx   edx, word ptr [rbx]
0x18000c5bf  mov     rcx, [r13+8]
0x18000c5c3  movzx   r14d, word ptr [rdi]
0x18000c5c7  call    cs:__imp_?tolower@?$ctype@G@std@@QEBAGG@Z; std::ctype<ushort>::tolower(ushort)
0x18000c5cd  mov     rcx, [r13+8]
0x18000c5d1  movzx   edx, r14w
0x18000c5d5  movzx   ebp, ax
0x18000c5d8  call    cs:__imp_?tolower@?$ctype@G@std@@QEBAGG@Z; std::ctype<ushort>::tolower(ushort)
0x18000c5de  cmp     ax, bp
0x18000c5e1  jnz     short loc_18000C62D
0x18000c5e3  add     rbx, 2
0x18000c5e7  add     rdi, 2
0x18000c5eb  jmp     short loc_18000C5AD
0x18000c5ed  cmp     rbx, [rsp+68h+arg_20]
0x18000c5f5  jnz     short loc_18000C62D
0x18000c5f7  mov     r15, rdi
0x18000c5fa  jmp     short loc_18000C62D
0x18000c5fc  mov     rax, rdx
0x18000c5ff  cmp     rax, rsi
0x18000c602  jz      short loc_18000C620
0x18000c604  cmp     rbx, [rsp+68h+arg_20]
0x18000c60c  jz      short loc_18000C62A
0x18000c60e  movzx   ecx, word ptr [rbx]
0x18000c611  cmp     [rax], cx
0x18000c614  jnz     short loc_18000C62D
0x18000c616  add     rbx, 2
0x18000c61a  add     rax, 2
0x18000c61e  jmp     short loc_18000C5FF
0x18000c620  cmp     rbx, [rsp+68h+arg_20]
0x18000c628  jnz     short loc_18000C62D
0x18000c62a  mov     r15, rax
0x18000c62d  mov     rax, r12
0x18000c630  mov     [r12], r15
0x18000c634  add     rsp, 28h
0x18000c638  pop     r15
0x18000c63a  pop     r14
0x18000c63c  pop     r13
0x18000c63e  pop     r12
0x18000c640  pop     rdi
0x18000c641  pop     rsi
0x18000c642  pop     rbp
0x18000c643  pop     rbx
0x18000c644  retn
```
