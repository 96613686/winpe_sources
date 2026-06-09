# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::assign(std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70> const &,unsigned __int64,unsigned __int64)

- ea: `0x18000bf0c`
- end: `0x18000bff8`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `236`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180003214`
- `0x180003284`
- `0x1800032f0`
- `0x180003354`
- `0x1800033c4`
- `0x18000c000`

## callees

- `0x180001434`
- `0x180001490`
- `0x18000b11c`
- `0x18000bf0c`
- `0x18000caf4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000bfd2`
- `msvcrt!memcpy_s` at `0x18000bfd2`

## pseudocode

```c
_QWORD *__fastcall std::string::assign(_QWORD *a1, _QWORD *a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v7; // rbx
  _QWORD *v8; // rax
  rsize_t v9; // rdx
  void **v10; // rsi
  void *v11; // rcx
  _QWORD *v12; // rax

  if ( a2[3] < a3 )
    std::_String_base::_Xran();
  v7 = a2[3] - a3;
  if ( a4 < v7 )
    v7 = a4;
  if ( a1 == a2 )
  {
    std::string::erase(a1, v7 + a3, 0xFFFFFFFFFFFFFFFFuLL);
    std::string::erase(a1, 0, a3);
    return a1;
  }
  if ( v7 == -1 )
    std::_String_base::_Xlen();
  if ( a1[4] < v7 )
  {
    std::string::_Copy((__int64)a1, v7, a1[3]);
    if ( !v7 )
      return a1;
    goto LABEL_11;
  }
  if ( v7 )
  {
LABEL_11:
    v8 = a2 + 1;
    if ( a2[4] >= 0x10u )
      v8 = (_QWORD *)*v8;
    v9 = a1[4];
    v10 = (void **)(a1 + 1);
    if ( v9 < 0x10 )
      v11 = a1 + 1;
    else
      v11 = *v10;
    memcpy_s(v11, v9, (char *)v8 + a3, v7);
    if ( a1[4] >= 0x10u )
      v10 = (void **)*v10;
    a1[3] = v7;
    *((_BYTE *)v10 + v7) = 0;
    return a1;
  }
  v12 = a1 + 1;
  if ( a1[4] >= 0x10u )
    v12 = (_QWORD *)*v12;
  a1[3] = 0;
  *(_BYTE *)v12 = 0;
  return a1;
}

```

## disassembly

```asm
0x18000bf0c  push    rbx
0x18000bf0e  push    rbp
0x18000bf0f  push    rsi
0x18000bf10  push    rdi
0x18000bf11  push    r14
0x18000bf13  sub     rsp, 20h
0x18000bf17  mov     r14, r9
0x18000bf1a  mov     rbp, r8
0x18000bf1d  mov     rsi, rdx
0x18000bf20  mov     rdi, rcx
0x18000bf23  cmp     [rdx+18h], r8
0x18000bf27  jnb     short loc_18000BF2E
0x18000bf29  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x18000bf2e  mov     rbx, [rsi+18h]
0x18000bf32  sub     rbx, rbp
0x18000bf35  cmp     r14, rbx
0x18000bf38  cmovb   rbx, r14
0x18000bf3c  cmp     rdi, rsi
0x18000bf3f  jnz     short loc_18000BF63
0x18000bf41  lea     rdx, [rbx+rbp]
0x18000bf45  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000bf49  mov     rcx, rdi
0x18000bf4c  call    ?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z; std::string::erase(unsigned __int64,unsigned __int64)
0x18000bf51  mov     r8, rbp
0x18000bf54  xor     edx, edx
0x18000bf56  mov     rcx, rdi
0x18000bf59  call    ?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z; std::string::erase(unsigned __int64,unsigned __int64)
0x18000bf5e  jmp     loc_18000BFEA
0x18000bf63  cmp     rbx, 0FFFFFFFFFFFFFFFEh
0x18000bf67  jbe     short loc_18000BF6E
0x18000bf69  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x18000bf6e  xor     r14d, r14d
0x18000bf71  cmp     [rdi+20h], rbx
0x18000bf75  jnb     short loc_18000BFAC
0x18000bf77  mov     r8, [rdi+18h]
0x18000bf7b  mov     rdx, rbx
0x18000bf7e  mov     rcx, rdi
0x18000bf81  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x18000bf86  test    rbx, rbx
0x18000bf89  jz      short loc_18000BFEA
0x18000bf8b  cmp     qword ptr [rsi+20h], 10h
0x18000bf90  lea     rax, [rsi+8]
0x18000bf94  jb      short loc_18000BF99
0x18000bf96  mov     rax, [rax]
0x18000bf99  mov     rdx, [rdi+20h]; DestinationSize
0x18000bf9d  lea     rsi, [rdi+8]
0x18000bfa1  cmp     rdx, 10h
0x18000bfa5  jb      short loc_18000BFC8
0x18000bfa7  mov     rcx, [rsi]
0x18000bfaa  jmp     short loc_18000BFCB
0x18000bfac  test    rbx, rbx
0x18000bfaf  jnz     short loc_18000BF8B
0x18000bfb1  cmp     qword ptr [rdi+20h], 10h
0x18000bfb6  lea     rax, [rdi+8]
0x18000bfba  jb      short loc_18000BFBF
0x18000bfbc  mov     rax, [rax]
0x18000bfbf  mov     [rdi+18h], r14
0x18000bfc3  mov     [rax], r14b
0x18000bfc6  jmp     short loc_18000BFEA
0x18000bfc8  mov     rcx, rsi; Destination
0x18000bfcb  lea     r8, [rax+rbp]; Source
0x18000bfcf  mov     r9, rbx; SourceSize
0x18000bfd2  call    cs:__imp_memcpy_s
0x18000bfd8  cmp     qword ptr [rdi+20h], 10h
0x18000bfdd  jb      short loc_18000BFE2
0x18000bfdf  mov     rsi, [rsi]
0x18000bfe2  mov     [rdi+18h], rbx
0x18000bfe6  mov     [rsi+rbx], r14b
0x18000bfea  mov     rax, rdi
0x18000bfed  add     rsp, 20h
0x18000bff1  pop     r14
0x18000bff3  pop     rdi
0x18000bff4  pop     rsi
0x18000bff5  pop     rbp
0x18000bff6  pop     rbx
0x18000bff7  retn
```
