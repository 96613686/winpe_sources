# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>::assign(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70> const &,unsigned __int64,unsigned __int64)

- ea: `0x1800039e8`
- end: `0x180003aea`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `258`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180003210`
- `0x180003330`

## callees

- `0x1800016a4`
- `0x180001700`
- `0x1800035a4`
- `0x1800039e8`
- `0x180003af0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003ac1`
- `msvcrt!memcpy_s` at `0x180003ac1`

## pseudocode

```c
_QWORD *__fastcall std::wstring::assign(_QWORD *a1, _QWORD *a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v7; // rdi
  _QWORD *v8; // rax
  unsigned __int64 v9; // rdx
  void **v10; // rsi
  void *v11; // rcx
  _QWORD *v12; // rcx

  if ( a2[3] < a3 )
    std::_String_base::_Xran();
  v7 = a2[3] - a3;
  if ( a4 < v7 )
    v7 = a4;
  if ( a1 == a2 )
  {
    std::wstring::erase(a1, v7 + a3, 0xFFFFFFFFFFFFFFFFuLL);
    std::wstring::erase(a1, 0, a3);
    return a1;
  }
  if ( v7 > 0x7FFFFFFFFFFFFFFELL )
    std::_String_base::_Xlen();
  if ( a1[4] < v7 )
  {
    std::wstring::_Copy((__int64)a1, v7, a1[3]);
    if ( !v7 )
      return a1;
    goto LABEL_11;
  }
  if ( v7 )
  {
LABEL_11:
    v8 = a2 + 1;
    if ( a2[4] >= 8u )
      v8 = (_QWORD *)*v8;
    v9 = a1[4];
    v10 = (void **)(a1 + 1);
    if ( v9 < 8 )
      v11 = a1 + 1;
    else
      v11 = *v10;
    memcpy_s(v11, 2 * v9, (char *)v8 + 2 * a3, 2 * v7);
    if ( a1[4] >= 8u )
      v10 = (void **)*v10;
    a1[3] = v7;
    *((_WORD *)v10 + v7) = 0;
    return a1;
  }
  v12 = a1 + 1;
  if ( a1[4] >= 8u )
    v12 = (_QWORD *)*v12;
  a1[3] = 0;
  *(_WORD *)v12 = 0;
  return a1;
}

```

## disassembly

```asm
0x1800039e8  push    rbx
0x1800039ea  push    rbp
0x1800039eb  push    rsi
0x1800039ec  push    rdi
0x1800039ed  push    r14
0x1800039ef  sub     rsp, 20h
0x1800039f3  mov     r14, r9
0x1800039f6  mov     rbp, r8
0x1800039f9  mov     rsi, rdx
0x1800039fc  mov     rbx, rcx
0x1800039ff  cmp     [rdx+18h], r8
0x180003a03  jnb     short loc_180003A0A
0x180003a05  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x180003a0a  mov     rdi, [rsi+18h]
0x180003a0e  sub     rdi, rbp
0x180003a11  cmp     r14, rdi
0x180003a14  cmovb   rdi, r14
0x180003a18  cmp     rbx, rsi
0x180003a1b  jnz     short loc_180003A3F
0x180003a1d  lea     rdx, [rdi+rbp]
0x180003a21  or      r8, 0FFFFFFFFFFFFFFFFh
0x180003a25  mov     rcx, rbx
0x180003a28  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x180003a2d  mov     r8, rbp
0x180003a30  xor     edx, edx
0x180003a32  mov     rcx, rbx
0x180003a35  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x180003a3a  jmp     loc_180003ADC
0x180003a3f  mov     rax, 7FFFFFFFFFFFFFFEh
0x180003a49  cmp     rdi, rax
0x180003a4c  jbe     short loc_180003A53
0x180003a4e  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x180003a53  cmp     [rbx+20h], rdi
0x180003a57  jnb     short loc_180003A8E
0x180003a59  mov     r8, [rbx+18h]
0x180003a5d  mov     rdx, rdi
0x180003a60  mov     rcx, rbx
0x180003a63  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180003a68  test    rdi, rdi
0x180003a6b  jz      short loc_180003ADC
0x180003a6d  cmp     qword ptr [rsi+20h], 8
0x180003a72  lea     rax, [rsi+8]
0x180003a76  jb      short loc_180003A7B
0x180003a78  mov     rax, [rax]
0x180003a7b  mov     rdx, [rbx+20h]
0x180003a7f  lea     rsi, [rbx+8]
0x180003a83  cmp     rdx, 8
0x180003a87  jb      short loc_180003AB0
0x180003a89  mov     rcx, [rsi]
0x180003a8c  jmp     short loc_180003AB3
0x180003a8e  test    rdi, rdi
0x180003a91  jnz     short loc_180003A6D
0x180003a93  cmp     qword ptr [rbx+20h], 8
0x180003a98  lea     rcx, [rbx+8]
0x180003a9c  jb      short loc_180003AA1
0x180003a9e  mov     rcx, [rcx]
0x180003aa1  xor     eax, eax
0x180003aa3  mov     qword ptr [rbx+18h], 0
0x180003aab  mov     [rcx], ax
0x180003aae  jmp     short loc_180003ADC
0x180003ab0  mov     rcx, rsi; Destination
0x180003ab3  lea     r14, [rdi+rdi]
0x180003ab7  add     rdx, rdx; DestinationSize
0x180003aba  mov     r9, r14; SourceSize
0x180003abd  lea     r8, [rax+rbp*2]; Source
0x180003ac1  call    cs:__imp_memcpy_s
0x180003ac7  cmp     qword ptr [rbx+20h], 8
0x180003acc  jb      short loc_180003AD1
0x180003ace  mov     rsi, [rsi]
0x180003ad1  xor     eax, eax
0x180003ad3  mov     [rbx+18h], rdi
0x180003ad7  mov     [r14+rsi], ax
0x180003adc  mov     rax, rbx
0x180003adf  add     rsp, 20h
0x180003ae3  pop     r14
0x180003ae5  pop     rdi
0x180003ae6  pop     rsi
0x180003ae7  pop     rbp
0x180003ae8  pop     rbx
0x180003ae9  retn
```
