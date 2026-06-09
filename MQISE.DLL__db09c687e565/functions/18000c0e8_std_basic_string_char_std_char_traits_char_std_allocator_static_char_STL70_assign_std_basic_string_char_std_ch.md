# std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>::assign(std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const &,unsigned __int64,unsigned __int64)

- ea: `0x18000c0e8`
- end: `0x18000c289`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b04c`

## callees

- `0x180001434`
- `0x180001490`
- `0x18000b11c`
- `0x18000c0e8`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000c179`
- `msvcrt!memmove_s` at `0x18000c1cf`
- `msvcrt!memmove_s` at `0x18000c179`
- `msvcrt!memmove_s` at `0x18000c1cf`
- `msvcrt!memcpy_s` at `0x18000c261`
- `msvcrt!memcpy_s` at `0x18000c261`

## pseudocode

```c
__int64 __fastcall std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>::assign(
        __int64 a1,
        _QWORD *a2,
        unsigned __int64 a3,
        rsize_t a4)
{
  unsigned __int64 v4; // rbp
  rsize_t v7; // rdi
  __int64 v8; // r14
  rsize_t v9; // r15
  rsize_t v10; // r9
  unsigned __int64 v11; // rdx
  _QWORD *v12; // rdi
  _QWORD *v13; // rax
  _QWORD *v14; // rcx
  __int64 v15; // rax
  unsigned __int64 v16; // r9
  rsize_t v17; // rdx
  void **v18; // rdi
  void *v19; // rcx
  char *v20; // rax
  unsigned __int64 v21; // rax
  _QWORD *v22; // rax
  rsize_t v23; // rdx
  void **v24; // r14
  void *v25; // rcx
  _QWORD *v26; // rax

  v4 = a3;
  if ( a2[3] < a3 )
    std::_String_base::_Xran();
  v7 = a2[3] - a3;
  if ( a4 < v7 )
    v7 = a4;
  if ( (_QWORD *)a1 == a2 )
  {
    v8 = -1;
    v9 = v7 + a3;
    if ( *(_QWORD *)(a1 + 24) < v7 + a3 )
      std::_String_base::_Xran();
    v10 = *(_QWORD *)(a1 + 24) - v9;
    if ( v10 != -1 )
    {
      if ( !v10 )
      {
LABEL_17:
        v16 = *(_QWORD *)(a1 + 24);
        if ( v16 < v4 )
          v4 = *(_QWORD *)(a1 + 24);
        if ( v4 )
        {
          v17 = *(_QWORD *)(a1 + 32);
          v18 = (void **)(a1 + 8);
          if ( v17 < 0x10 )
          {
            v19 = (void *)(a1 + 8);
            v20 = (char *)(a1 + 8);
          }
          else
          {
            v19 = *v18;
            v20 = (char *)*v18;
          }
          memmove_s(v19, v17, &v20[v4], v16 - v4);
          v21 = *(_QWORD *)(a1 + 24) - v4;
          if ( *(_QWORD *)(a1 + 32) >= 0x10u )
            v18 = (void **)*v18;
          *(_QWORD *)(a1 + 24) = v21;
          *((_BYTE *)v18 + v21) = 0;
        }
        return a1;
      }
      v8 = *(_QWORD *)(a1 + 24) - v9;
    }
    v11 = *(_QWORD *)(a1 + 32);
    v12 = (_QWORD *)(a1 + 8);
    if ( v11 < 0x10 )
    {
      v13 = (_QWORD *)(a1 + 8);
      v14 = (_QWORD *)(a1 + 8);
    }
    else
    {
      v13 = (_QWORD *)*v12;
      v14 = (_QWORD *)*v12;
    }
    memmove_s((char *)v13 + v9, v11 - v9, (char *)v14 + v9 + v8, v10 - v8);
    v15 = *(_QWORD *)(a1 + 24) - v8;
    if ( *(_QWORD *)(a1 + 32) >= 0x10u )
      v12 = (_QWORD *)*v12;
    *(_QWORD *)(a1 + 24) = v15;
    *((_BYTE *)v12 + v15) = 0;
    goto LABEL_17;
  }
  if ( v7 == -1 )
    std::_String_base::_Xlen();
  if ( *(_QWORD *)(a1 + 32) < v7 )
  {
    std::string::_Copy(a1, v7, *(_QWORD *)(a1 + 24));
    if ( !v7 )
      return a1;
    goto LABEL_30;
  }
  if ( v7 )
  {
LABEL_30:
    v22 = a2 + 1;
    if ( a2[4] >= 0x10u )
      v22 = (_QWORD *)*v22;
    v23 = *(_QWORD *)(a1 + 32);
    v24 = (void **)(a1 + 8);
    if ( v23 < 0x10 )
      v25 = (void *)(a1 + 8);
    else
      v25 = *v24;
    memcpy_s(v25, v23, (char *)v22 + v4, v7);
    if ( *(_QWORD *)(a1 + 32) >= 0x10u )
      v24 = (void **)*v24;
    *(_QWORD *)(a1 + 24) = v7;
    *((_BYTE *)v24 + v7) = 0;
    return a1;
  }
  v26 = (_QWORD *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 32) >= 0x10u )
    v26 = (_QWORD *)*v26;
  *(_QWORD *)(a1 + 24) = 0;
  *(_BYTE *)v26 = 0;
  return a1;
}

```

## disassembly

```asm
0x18000c0e8  push    rbx
0x18000c0ea  push    rbp
0x18000c0eb  push    rsi
0x18000c0ec  push    rdi
0x18000c0ed  push    r14
0x18000c0ef  push    r15
0x18000c0f1  sub     rsp, 28h
0x18000c0f5  mov     rsi, r9
0x18000c0f8  mov     rbp, r8
0x18000c0fb  mov     r14, rdx
0x18000c0fe  mov     rbx, rcx
0x18000c101  cmp     [rdx+18h], r8
0x18000c105  jnb     short loc_18000C10C
0x18000c107  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x18000c10c  mov     rdi, [r14+18h]
0x18000c110  sub     rdi, rbp
0x18000c113  cmp     rsi, rdi
0x18000c116  cmovb   rdi, rsi
0x18000c11a  cmp     rbx, r14
0x18000c11d  jnz     loc_18000C1F3
0x18000c123  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000c127  lea     r15, [rdi+rbp]
0x18000c12b  cmp     [rbx+18h], r15
0x18000c12f  jnb     short loc_18000C136
0x18000c131  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x18000c136  mov     r9, [rbx+18h]
0x18000c13a  xor     esi, esi
0x18000c13c  sub     r9, r15
0x18000c13f  cmp     r9, r14
0x18000c142  jnb     short loc_18000C14C
0x18000c144  test    r9, r9
0x18000c147  jz      short loc_18000C198
0x18000c149  mov     r14, r9
0x18000c14c  mov     rdx, [rbx+20h]
0x18000c150  lea     rdi, [rbx+8]
0x18000c154  cmp     rdx, 10h
0x18000c158  jb      short loc_18000C162
0x18000c15a  mov     rax, [rdi]
0x18000c15d  mov     rcx, rax
0x18000c160  jmp     short loc_18000C168
0x18000c162  mov     rax, rdi
0x18000c165  mov     rcx, rdi
0x18000c168  lea     r8, [r15+rcx]
0x18000c16c  sub     r9, r14; SourceSize
0x18000c16f  add     r8, r14; Source
0x18000c172  lea     rcx, [r15+rax]; Destination
0x18000c176  sub     rdx, r15; DestinationSize
0x18000c179  call    cs:__imp_memmove_s
0x18000c17f  mov     rax, [rbx+18h]
0x18000c183  sub     rax, r14
0x18000c186  cmp     qword ptr [rbx+20h], 10h
0x18000c18b  jb      short loc_18000C190
0x18000c18d  mov     rdi, [rdi]
0x18000c190  mov     [rbx+18h], rax
0x18000c194  mov     [rax+rdi], sil
0x18000c198  mov     r9, [rbx+18h]
0x18000c19c  cmp     r9, rbp
0x18000c19f  cmovb   rbp, r9
0x18000c1a3  test    rbp, rbp
0x18000c1a6  jz      loc_18000C279
0x18000c1ac  mov     rdx, [rbx+20h]; DestinationSize
0x18000c1b0  lea     rdi, [rbx+8]
0x18000c1b4  cmp     rdx, 10h
0x18000c1b8  jb      short loc_18000C1C2
0x18000c1ba  mov     rcx, [rdi]
0x18000c1bd  mov     rax, rcx
0x18000c1c0  jmp     short loc_18000C1C8
0x18000c1c2  mov     rcx, rdi; Destination
0x18000c1c5  mov     rax, rdi
0x18000c1c8  sub     r9, rbp; SourceSize
0x18000c1cb  lea     r8, [rax+rbp]; Source
0x18000c1cf  call    cs:__imp_memmove_s
0x18000c1d5  mov     rax, [rbx+18h]
0x18000c1d9  sub     rax, rbp
0x18000c1dc  cmp     qword ptr [rbx+20h], 10h
0x18000c1e1  jb      short loc_18000C1E6
0x18000c1e3  mov     rdi, [rdi]
0x18000c1e6  mov     [rbx+18h], rax
0x18000c1ea  mov     [rax+rdi], sil
0x18000c1ee  jmp     loc_18000C279
0x18000c1f3  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x18000c1f7  jbe     short loc_18000C1FE
0x18000c1f9  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x18000c1fe  xor     esi, esi
0x18000c200  cmp     [rbx+20h], rdi
0x18000c204  jnb     short loc_18000C23B
0x18000c206  mov     r8, [rbx+18h]
0x18000c20a  mov     rdx, rdi
0x18000c20d  mov     rcx, rbx
0x18000c210  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x18000c215  test    rdi, rdi
0x18000c218  jz      short loc_18000C279
0x18000c21a  cmp     qword ptr [r14+20h], 10h
0x18000c21f  lea     rax, [r14+8]
0x18000c223  jb      short loc_18000C228
0x18000c225  mov     rax, [rax]
0x18000c228  mov     rdx, [rbx+20h]; DestinationSize
0x18000c22c  lea     r14, [rbx+8]
0x18000c230  cmp     rdx, 10h
0x18000c234  jb      short loc_18000C257
0x18000c236  mov     rcx, [r14]
0x18000c239  jmp     short loc_18000C25A
0x18000c23b  test    rdi, rdi
0x18000c23e  jnz     short loc_18000C21A
0x18000c240  cmp     qword ptr [rbx+20h], 10h
0x18000c245  lea     rax, [rbx+8]
0x18000c249  jb      short loc_18000C24E
0x18000c24b  mov     rax, [rax]
0x18000c24e  mov     [rbx+18h], rsi
0x18000c252  mov     [rax], sil
0x18000c255  jmp     short loc_18000C279
0x18000c257  mov     rcx, r14; Destination
0x18000c25a  lea     r8, [rax+rbp]; Source
0x18000c25e  mov     r9, rdi; SourceSize
0x18000c261  call    cs:__imp_memcpy_s
0x18000c267  cmp     qword ptr [rbx+20h], 10h
0x18000c26c  jb      short loc_18000C271
0x18000c26e  mov     r14, [r14]
0x18000c271  mov     [rbx+18h], rdi
0x18000c275  mov     [r14+rdi], sil
0x18000c279  mov     rax, rbx
0x18000c27c  add     rsp, 28h
0x18000c280  pop     r15
0x18000c282  pop     r14
0x18000c284  pop     rdi
0x18000c285  pop     rsi
0x18000c286  pop     rbp
0x18000c287  pop     rbx
0x18000c288  retn
```
