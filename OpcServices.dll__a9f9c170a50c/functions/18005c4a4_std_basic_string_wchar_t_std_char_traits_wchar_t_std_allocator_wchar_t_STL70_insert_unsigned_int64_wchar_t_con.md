# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>::insert(unsigned __int64,wchar_t const *,unsigned __int64)

- ea: `0x18005c4a4`
- end: `0x18005c5da`
- name: `?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_KPEB_W0@Z`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18005c2e0`

## callees

- `0x18001c4b0`
- `0x18005c4a4`
- `0x18005c5f0`
- `0x18005d81c`
- `0x1800cdb60`
- `0x1800cdbbc`

## import_xrefs

- `msvcrt!memmove_s` at `0x18005c542`
- `msvcrt!memmove_s` at `0x18005c542`
- `msvcrt!memcpy_s` at `0x18005c566`
- `msvcrt!memcpy_s` at `0x18005c566`

## pseudocode

```c
_QWORD *__fastcall std::wstring::insert(_QWORD *a1, unsigned __int64 a2, _BYTE *a3, unsigned __int64 a4)
{
  unsigned __int64 v8; // rbp
  _QWORD *v9; // rdi
  unsigned __int64 v10; // rdx
  __int64 v11; // r12
  _QWORD *v12; // rcx
  _QWORD *v13; // rax
  unsigned __int64 v14; // rdx
  _QWORD *v15; // rax
  _QWORD *v17; // rax

  if ( (unsigned __int8)std::wstring::_Inside(a1, a3) )
  {
    v17 = a1 + 1;
    if ( a1[4] >= 8u )
      v17 = (_QWORD *)*v17;
    return std::wstring::insert(a1, a2, a1, (a3 - (_BYTE *)v17) >> 1, a4);
  }
  else
  {
    if ( a1[3] < a2 )
      std::_String_base::_Xran();
    if ( ~a1[3] <= a4 )
      std::_String_base::_Xlen();
    if ( a4 )
    {
      v8 = a4 + a1[3];
      if ( (unsigned __int8)std::wstring::_Grow(a1, v8, 0) )
      {
        v9 = a1 + 1;
        v10 = a1[4];
        v11 = 2 * a2;
        if ( v10 < 8 )
        {
          v12 = a1 + 1;
          v13 = a1 + 1;
        }
        else
        {
          v12 = (_QWORD *)*v9;
          v13 = (_QWORD *)*v9;
        }
        memmove_s((char *)v12 + 2 * a2 + 2 * a4, 2 * (v10 - a2 - a4), (char *)v13 + v11, 2 * (a1[3] - a2));
        v14 = a1[4];
        if ( v14 < 8 )
          v15 = a1 + 1;
        else
          v15 = (_QWORD *)*v9;
        memcpy_s((char *)v15 + v11, 2 * (v14 - a2), a3, 2 * a4);
        if ( a1[4] >= 8u )
          v9 = (_QWORD *)*v9;
        a1[3] = v8;
        *((_WORD *)v9 + v8) = 0;
      }
    }
    return a1;
  }
}

```

## disassembly

```asm
0x18005c4a4  push    rbx
0x18005c4a6  push    rbp
0x18005c4a7  push    rsi
0x18005c4a8  push    rdi
0x18005c4a9  push    r12
0x18005c4ab  push    r14
0x18005c4ad  push    r15
0x18005c4af  sub     rsp, 30h
0x18005c4b3  mov     r15, rdx
0x18005c4b6  mov     r14, r9
0x18005c4b9  mov     rdx, r8
0x18005c4bc  mov     rsi, r8
0x18005c4bf  mov     rbx, rcx
0x18005c4c2  call    ?_Inside@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAA_NPEB_W@Z; std::wstring::_Inside(wchar_t const *)
0x18005c4c7  test    al, al
0x18005c4c9  jnz     loc_18005C59F
0x18005c4cf  cmp     [rbx+18h], r15
0x18005c4d3  jb      loc_18005C5CB
0x18005c4d9  mov     rax, [rbx+18h]
0x18005c4dd  not     rax
0x18005c4e0  cmp     rax, r14
0x18005c4e3  jbe     loc_18005C5D5
0x18005c4e9  test    r14, r14
0x18005c4ec  jz      loc_18005C580
0x18005c4f2  mov     rbp, [rbx+18h]
0x18005c4f6  xor     r8d, r8d
0x18005c4f9  add     rbp, r14
0x18005c4fc  mov     rcx, rbx
0x18005c4ff  mov     rdx, rbp
0x18005c502  call    ?_Grow@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x18005c507  test    al, al
0x18005c509  jz      short loc_18005C580
0x18005c50b  mov     r9, [rbx+18h]
0x18005c50f  lea     rdi, [rbx+8]
0x18005c513  mov     rdx, [rbx+20h]
0x18005c517  lea     r12, [r15+r15]
0x18005c51b  sub     r9, r15
0x18005c51e  cmp     rdx, 8
0x18005c522  jb      short loc_18005C592
0x18005c524  mov     rcx, [rdi]
0x18005c527  mov     rax, rcx
0x18005c52a  sub     rdx, r15
0x18005c52d  lea     r8, [r12+rax]; Source
0x18005c531  sub     rdx, r14
0x18005c534  lea     rax, [r15+r14]
0x18005c538  add     rdx, rdx; DestinationSize
0x18005c53b  lea     rcx, [rcx+rax*2]; Destination
0x18005c53f  add     r9, r9; SourceSize
0x18005c542  call    cs:__imp_memmove_s
0x18005c548  mov     rdx, [rbx+20h]
0x18005c54c  cmp     rdx, 8
0x18005c550  jb      short loc_18005C59A
0x18005c552  mov     rax, [rdi]
0x18005c555  sub     rdx, r15
0x18005c558  lea     r9, [r14+r14]; SourceSize
0x18005c55c  add     rdx, rdx; DestinationSize
0x18005c55f  lea     rcx, [r12+rax]; Destination
0x18005c563  mov     r8, rsi; Source
0x18005c566  call    cs:__imp_memcpy_s
0x18005c56c  cmp     qword ptr [rbx+20h], 8
0x18005c571  jb      short loc_18005C576
0x18005c573  mov     rdi, [rdi]
0x18005c576  xor     eax, eax
0x18005c578  mov     [rbx+18h], rbp
0x18005c57c  mov     [rdi+rbp*2], ax
0x18005c580  mov     rax, rbx
0x18005c583  add     rsp, 30h
0x18005c587  pop     r15
0x18005c589  pop     r14
0x18005c58b  pop     r12
0x18005c58d  pop     rdi
0x18005c58e  pop     rsi
0x18005c58f  pop     rbp
0x18005c590  pop     rbx
0x18005c591  retn
0x18005c592  mov     rcx, rdi
0x18005c595  mov     rax, rdi
0x18005c598  jmp     short loc_18005C52A
0x18005c59a  mov     rax, rdi
0x18005c59d  jmp     short loc_18005C555
0x18005c59f  cmp     qword ptr [rbx+20h], 8
0x18005c5a4  lea     rax, [rbx+8]
0x18005c5a8  jb      short loc_18005C5AD
0x18005c5aa  mov     rax, [rax]
0x18005c5ad  sub     rsi, rax
0x18005c5b0  mov     [rsp+68h+var_48], r14
0x18005c5b5  sar     rsi, 1
0x18005c5b8  mov     r8, rbx
0x18005c5bb  mov     r9, rsi
0x18005c5be  mov     rdx, r15
0x18005c5c1  mov     rcx, rbx
0x18005c5c4  call    ?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_KAEBV12@00@Z; std::wstring::insert(unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x18005c5c9  jmp     short loc_18005C583
0x18005c5cb  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x18005c5d0  jmp     loc_18005C4D9
0x18005c5d5  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
```
