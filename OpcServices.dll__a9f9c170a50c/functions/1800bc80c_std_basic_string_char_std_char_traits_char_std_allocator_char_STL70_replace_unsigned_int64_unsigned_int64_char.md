# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::replace(unsigned __int64,unsigned __int64,char const *,unsigned __int64)

- ea: `0x1800bc80c`
- end: `0x1800bc9a1`
- name: `?replace@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0PEBD0@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800bc774`

## callees

- `0x1800207b0`
- `0x1800222b4`
- `0x180083c7c`
- `0x1800bc80c`
- `0x1800cdb60`
- `0x1800cdbbc`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800bc8e7`
- `msvcrt!memmove_s` at `0x1800bc94f`
- `msvcrt!memmove_s` at `0x1800bc8e7`
- `msvcrt!memmove_s` at `0x1800bc94f`
- `msvcrt!memcpy_s` at `0x1800bc974`
- `msvcrt!memcpy_s` at `0x1800bc974`

## pseudocode

```c
_QWORD *__fastcall std::string::replace(_QWORD *a1, unsigned __int64 a2, rsize_t a3, _BYTE *a4, rsize_t SourceSize)
{
  _QWORD *v9; // rax
  _QWORD *v11; // rdi
  rsize_t v12; // r15
  unsigned __int64 v13; // rdx
  _QWORD *v14; // rax
  _QWORD *v15; // rcx
  rsize_t v16; // r13
  unsigned __int64 v17; // rdx
  _QWORD *v18; // rax
  _QWORD *v19; // rcx
  unsigned __int64 v20; // rdx
  _QWORD *v21; // rax

  if ( (unsigned __int8)std::string::_Inside(a1, a4) )
  {
    v9 = a1 + 1;
    if ( a1[4] >= 0x10u )
      v9 = (_QWORD *)*v9;
    return std::string::replace(a1, a2, a3, a1, a4 - (_BYTE *)v9, SourceSize);
  }
  else
  {
    if ( a1[3] < a2 )
      std::_String_base::_Xran();
    if ( a1[3] - a2 < a3 )
      a3 = a1[3] - a2;
    if ( ~SourceSize <= a1[3] - a3 )
      std::_String_base::_Xlen();
    v11 = a1 + 1;
    v12 = a1[3] - a2 - a3;
    if ( SourceSize < a3 )
    {
      v13 = a1[4];
      if ( v13 < 0x10 )
      {
        v14 = a1 + 1;
        v15 = a1 + 1;
      }
      else
      {
        v14 = (_QWORD *)*v11;
        v15 = (_QWORD *)*v11;
      }
      memmove_s((char *)v14 + a2 + SourceSize, v13 - a2 - SourceSize, (char *)v15 + a2 + a3, a1[3] - a2 - a3);
    }
    if ( SourceSize || a3 )
    {
      v16 = SourceSize + a1[3] - a3;
      if ( (unsigned __int8)std::string::_Grow(a1, v16, 0) )
      {
        if ( a3 < SourceSize )
        {
          v17 = a1[4];
          v11 = a1 + 1;
          if ( v17 < 0x10 )
          {
            v18 = a1 + 1;
            v19 = a1 + 1;
          }
          else
          {
            v18 = (_QWORD *)*v11;
            v19 = (_QWORD *)*v11;
          }
          memmove_s((char *)v18 + a2 + SourceSize, v17 - a2 - SourceSize, (char *)v19 + a2 + a3, v12);
        }
        v20 = a1[4];
        if ( v20 < 0x10 )
          v21 = v11;
        else
          v21 = (_QWORD *)*v11;
        memcpy_s((char *)v21 + a2, v20 - a2, a4, SourceSize);
        if ( a1[4] >= 0x10u )
          v11 = (_QWORD *)*v11;
        a1[3] = v16;
        *((_BYTE *)v11 + v16) = 0;
      }
    }
    return a1;
  }
}

```

## disassembly

```asm
0x1800bc80c  push    rbx
0x1800bc80e  push    rbp
0x1800bc80f  push    rsi
0x1800bc810  push    rdi
0x1800bc811  push    r12
0x1800bc813  push    r13
0x1800bc815  push    r14
0x1800bc817  push    r15
0x1800bc819  sub     rsp, 38h
0x1800bc81d  mov     rbp, rdx
0x1800bc820  mov     r12, r9
0x1800bc823  mov     rdx, r9
0x1800bc826  mov     rsi, r8
0x1800bc829  mov     rbx, rcx
0x1800bc82c  call    ?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAA_NPEBD@Z; std::string::_Inside(char const *)
0x1800bc831  test    al, al
0x1800bc833  jz      short loc_1800BC86E
0x1800bc835  cmp     qword ptr [rbx+20h], 10h
0x1800bc83a  lea     rax, [rbx+8]
0x1800bc83e  jb      short loc_1800BC843
0x1800bc840  mov     rax, [rax]
0x1800bc843  sub     r12, rax
0x1800bc846  mov     r9, rbx
0x1800bc849  mov     rax, [rsp+78h+SourceSize]
0x1800bc851  mov     r8, rsi
0x1800bc854  mov     [rsp+78h+var_50], rax
0x1800bc859  mov     rdx, rbp
0x1800bc85c  mov     rcx, rbx
0x1800bc85f  mov     [rsp+78h+var_58], r12
0x1800bc864  call    ?replace@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0AEBV12@00@Z; std::string::replace(unsigned __int64,unsigned __int64,std::string const &,unsigned __int64,unsigned __int64)
0x1800bc869  jmp     loc_1800BC990
0x1800bc86e  cmp     [rbx+18h], rbp
0x1800bc872  jnb     short loc_1800BC879
0x1800bc874  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x1800bc879  mov     rcx, [rbx+18h]
0x1800bc87d  mov     r14, [rsp+78h+SourceSize]
0x1800bc885  mov     rax, rcx
0x1800bc888  sub     rax, rbp
0x1800bc88b  cmp     rax, rsi
0x1800bc88e  cmovb   rsi, rax
0x1800bc892  mov     rax, r14
0x1800bc895  not     rax
0x1800bc898  sub     rcx, rsi
0x1800bc89b  cmp     rax, rcx
0x1800bc89e  ja      short loc_1800BC8A5
0x1800bc8a0  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x1800bc8a5  mov     r15, [rbx+18h]
0x1800bc8a9  lea     rdi, [rbx+8]
0x1800bc8ad  sub     r15, rbp
0x1800bc8b0  sub     r15, rsi
0x1800bc8b3  cmp     r14, rsi
0x1800bc8b6  jnb     short loc_1800BC8ED
0x1800bc8b8  mov     rdx, [rbx+20h]
0x1800bc8bc  cmp     rdx, 10h
0x1800bc8c0  jb      short loc_1800BC8CA
0x1800bc8c2  mov     rax, [rdi]
0x1800bc8c5  mov     rcx, rax
0x1800bc8c8  jmp     short loc_1800BC8D0
0x1800bc8ca  mov     rax, rdi
0x1800bc8cd  mov     rcx, rdi
0x1800bc8d0  lea     r8, [rcx+rbp]
0x1800bc8d4  sub     rdx, rbp
0x1800bc8d7  lea     rcx, [rax+rbp]
0x1800bc8db  add     r8, rsi; Source
0x1800bc8de  add     rcx, r14; Destination
0x1800bc8e1  sub     rdx, r14; DestinationSize
0x1800bc8e4  mov     r9, r15; SourceSize
0x1800bc8e7  call    cs:__imp_memmove_s
0x1800bc8ed  test    r14, r14
0x1800bc8f0  jnz     short loc_1800BC8FB
0x1800bc8f2  test    rsi, rsi
0x1800bc8f5  jz      loc_1800BC98D
0x1800bc8fb  mov     r13, [rbx+18h]
0x1800bc8ff  xor     r8d, r8d
0x1800bc902  sub     r13, rsi
0x1800bc905  mov     rcx, rbx
0x1800bc908  add     r13, r14
0x1800bc90b  mov     rdx, r13
0x1800bc90e  call    ?_Grow@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAA_N_K_N@Z; std::string::_Grow(unsigned __int64,bool)
0x1800bc913  test    al, al
0x1800bc915  jz      short loc_1800BC98D
0x1800bc917  cmp     rsi, r14
0x1800bc91a  jnb     short loc_1800BC955
0x1800bc91c  mov     rdx, [rbx+20h]
0x1800bc920  lea     rdi, [rbx+8]
0x1800bc924  cmp     rdx, 10h
0x1800bc928  jb      short loc_1800BC932
0x1800bc92a  mov     rax, [rdi]
0x1800bc92d  mov     rcx, rax
0x1800bc930  jmp     short loc_1800BC938
0x1800bc932  mov     rax, rdi
0x1800bc935  mov     rcx, rdi
0x1800bc938  lea     r8, [rcx+rbp]
0x1800bc93c  sub     rdx, rbp
0x1800bc93f  lea     rcx, [rax+rbp]
0x1800bc943  add     r8, rsi; Source
0x1800bc946  add     rcx, r14; Destination
0x1800bc949  sub     rdx, r14; DestinationSize
0x1800bc94c  mov     r9, r15; SourceSize
0x1800bc94f  call    cs:__imp_memmove_s
0x1800bc955  mov     rdx, [rbx+20h]
0x1800bc959  cmp     rdx, 10h
0x1800bc95d  jb      short loc_1800BC964
0x1800bc95f  mov     rax, [rdi]
0x1800bc962  jmp     short loc_1800BC967
0x1800bc964  mov     rax, rdi
0x1800bc967  sub     rdx, rbp; DestinationSize
0x1800bc96a  lea     rcx, [rax+rbp]; Destination
0x1800bc96e  mov     r9, r14; SourceSize
0x1800bc971  mov     r8, r12; Source
0x1800bc974  call    cs:__imp_memcpy_s
0x1800bc97a  cmp     qword ptr [rbx+20h], 10h
0x1800bc97f  jb      short loc_1800BC984
0x1800bc981  mov     rdi, [rdi]
0x1800bc984  mov     [rbx+18h], r13
0x1800bc988  mov     byte ptr [rdi+r13], 0
0x1800bc98d  mov     rax, rbx
0x1800bc990  add     rsp, 38h
0x1800bc994  pop     r15
0x1800bc996  pop     r14
0x1800bc998  pop     r13
0x1800bc99a  pop     r12
0x1800bc99c  pop     rdi
0x1800bc99d  pop     rsi
0x1800bc99e  pop     rbp
0x1800bc99f  pop     rbx
0x1800bc9a0  retn
```
