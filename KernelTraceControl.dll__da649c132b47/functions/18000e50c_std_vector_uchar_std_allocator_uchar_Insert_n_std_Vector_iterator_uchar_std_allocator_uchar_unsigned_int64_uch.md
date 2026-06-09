# std::vector<uchar,std::allocator<uchar>>::_Insert_n(std::_Vector_iterator<uchar,std::allocator<uchar>>,unsigned __int64,uchar const &)

- ea: `0x18000e50c`
- end: `0x18000e76a`
- name: `?_Insert_n@?$vector@EV?$allocator@E@std@@@std@@IEAAXV?$_Vector_iterator@EV?$allocator@E@std@@@2@_KAEBE@Z`
- size: `606`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180008d5c`

## callees

- `0x18000252c`
- `0x18000e50c`
- `0x18000f438`
- `0x180010f84`
- `0x18002687c`
- `0x1800268f4`
- `0x180026f66`
- `0x180026f6c`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000e638`
- `msvcrt!memmove_s` at `0x18000e668`
- `msvcrt!memmove_s` at `0x18000e6ca`
- `msvcrt!memmove_s` at `0x18000e712`
- `msvcrt!memmove_s` at `0x18000e736`
- `msvcrt!memmove_s` at `0x18000e638`
- `msvcrt!memmove_s` at `0x18000e668`
- `msvcrt!memmove_s` at `0x18000e6ca`
- `msvcrt!memmove_s` at `0x18000e712`
- `msvcrt!memmove_s` at `0x18000e736`

## pseudocode

```c
char *__fastcall std::vector<unsigned char>::_Insert_n(__int64 a1, char *a2, rsize_t a3, char *a4)
{
  char *result; // rax
  char v8; // r9
  __int64 v9; // rdx
  rsize_t v10; // r8
  __int64 v11; // rax
  __int64 v12; // rax
  size_t v13; // r14
  __int64 v14; // rax
  __int64 v15; // rax
  char *v16; // rax
  char *v17; // r15
  _BYTE *v18; // r8
  rsize_t v19; // rdx
  char *v20; // r12
  __int64 v21; // rcx
  rsize_t v22; // rdx
  void *v23; // rcx
  __int64 v24; // rax
  rsize_t v25; // rdi
  __int64 v26; // r14
  rsize_t v27; // r14
  _BYTE *v28; // rcx
  size_t v29; // r8
  char *v30; // rdx
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-40h] BYREF
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h] BYREF
  char Val; // [rsp+70h] [rbp+8h]
  char *v34; // [rsp+80h] [rbp+18h] BYREF

  result = (char *)&retaddr;
  v8 = *a4;
  Val = v8;
  LOBYTE(v34) = v8;
  v9 = *(_QWORD *)(a1 + 8);
  if ( v9 )
    v10 = *(_QWORD *)(a1 + 24) - v9;
  else
    v10 = 0;
  if ( a3 )
  {
    if ( v9 )
      v11 = *(_QWORD *)(a1 + 16) - v9;
    else
      v11 = 0;
    if ( ~v11 < a3 )
      std::vector<_GUID>::_Xlen(a1, v9, v10);
    if ( v9 )
      v12 = *(_QWORD *)(a1 + 16) - v9;
    else
      v12 = 0;
    if ( v10 >= a3 + v12 )
    {
      v26 = *(_QWORD *)(a1 + 16);
      if ( v26 - (__int64)a2 >= a3 )
      {
        memmove_s(*(void *const *)(a1 + 16), a3, (const void *const)(v26 - a3), a3);
        *(_QWORD *)(a1 + 16) = a3 + v26;
        if ( (__int64)(v26 - (_QWORD)a2 - a3) > 0 )
          memmove_s(&a2[a3], v26 - (_QWORD)a2 - a3, a2, v26 - (_QWORD)a2 - a3);
        v30 = &a2[a3];
      }
      else
      {
        v27 = v26 - (_QWORD)a2;
        if ( v27 )
        {
          memmove_s(&a2[a3], v27, a2, v27);
          v8 = Val;
        }
        try
        {
          v28 = *(_BYTE **)(a1 + 16);
          v29 = a3 + a2 - v28;
          if ( v29 )
          {
            LOBYTE(v9) = v8;
            memset_0(v28, v9, v29);
          }
        }
        catch ( ... )
        {
          throw;
        }
        *(_QWORD *)(a1 + 16) += a3;
        v30 = (char *)(*(_QWORD *)(a1 + 16) - a3);
      }
      return (char *)std::fill<unsigned char *,unsigned char>(a2, v30, &v34);
    }
    else
    {
      v13 = 0;
      if ( ~(v10 >> 1) >= v10 )
        v13 = v10 + (v10 >> 1);
      if ( v9 )
        v14 = *(_QWORD *)(a1 + 16) - v9;
      else
        v14 = 0;
      if ( v13 < a3 + v14 )
      {
        if ( v9 )
          v15 = *(_QWORD *)(a1 + 16) - v9;
        else
          v15 = 0;
        v13 = v15 + a3;
      }
      if ( v13 && !(0xFFFFFFFFFFFFFFFFuLL / v13) )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, 0);
        throw (std::bad_alloc *)pExceptionObject;
      }
      v16 = (char *)operator new(v13);
      v17 = v16;
      v34 = v16;
      try
      {
        v18 = *(_BYTE **)(a1 + 8);
        v19 = a2 - v18;
        v20 = &v16[a2 - v18];
        if ( a2 != v18 )
          memmove_s(v16, v19, v18, a2 - v18);
        LOBYTE(v19) = Val;
        memset_0(v20, v19, a3);
        v22 = *(_QWORD *)(a1 + 16) - (_QWORD)a2;
        if ( v22 )
          memmove_s(&v20[a3], v22, a2, v22);
      }
      catch ( ... )
      {
        std::allocator<unsigned int>::deallocate(v21, v34);
        throw;
      }
      v23 = *(void **)(a1 + 8);
      if ( v23 )
        v24 = *(_QWORD *)(a1 + 16) - (_QWORD)v23;
      else
        v24 = 0;
      v25 = v24 + a3;
      if ( v23 )
        operator delete(v23);
      *(_QWORD *)(a1 + 24) = &v17[v13];
      result = &v17[v25];
      *(_QWORD *)(a1 + 16) = &v17[v25];
      *(_QWORD *)(a1 + 8) = v17;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e50c  mov     rax, rsp
0x18000e50f  push    rdi
0x18000e510  push    r12
0x18000e512  push    r13
0x18000e514  push    r14
0x18000e516  push    r15
0x18000e518  sub     rsp, 40h
0x18000e51c  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18000e524  mov     [rax+10h], rbx
0x18000e528  mov     [rax+20h], rsi
0x18000e52c  mov     rdi, r8
0x18000e52f  mov     rbx, rdx
0x18000e532  mov     rsi, rcx
0x18000e535  mov     r9b, [r9]
0x18000e538  mov     [rax+8], r9b
0x18000e53c  mov     [rax+18h], r9b
0x18000e540  mov     rdx, [rcx+8]
0x18000e544  test    rdx, rdx
0x18000e547  jnz     short loc_18000E54E
0x18000e549  xor     r8d, r8d
0x18000e54c  jmp     short loc_18000E555
0x18000e54e  mov     r8, [rcx+18h]
0x18000e552  sub     r8, rdx
0x18000e555  test    rdi, rdi
0x18000e558  jz      loc_18000E750
0x18000e55e  test    rdx, rdx
0x18000e561  jnz     short loc_18000E567
0x18000e563  xor     eax, eax
0x18000e565  jmp     short loc_18000E56E
0x18000e567  mov     rax, [rcx+10h]
0x18000e56b  sub     rax, rdx
0x18000e56e  not     rax
0x18000e571  cmp     rax, rdi
0x18000e574  jnb     short loc_18000E57C
0x18000e576  call    ?_Xlen@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@KAXXZ; std::vector<_GUID>::_Xlen(void)
0x18000e57c  test    rdx, rdx
0x18000e57f  jnz     short loc_18000E585
0x18000e581  xor     eax, eax
0x18000e583  jmp     short loc_18000E58C
0x18000e585  mov     rax, [rcx+10h]
0x18000e589  sub     rax, rdx
0x18000e58c  add     rax, rdi
0x18000e58f  cmp     r8, rax
0x18000e592  jnb     loc_18000E6A9
0x18000e598  mov     rax, r8
0x18000e59b  shr     rax, 1
0x18000e59e  mov     rcx, rax
0x18000e5a1  not     rcx
0x18000e5a4  add     rax, r8
0x18000e5a7  xor     r14d, r14d
0x18000e5aa  cmp     rcx, r8
0x18000e5ad  cmovnb  r14, rax
0x18000e5b1  test    rdx, rdx
0x18000e5b4  jnz     short loc_18000E5BA
0x18000e5b6  xor     eax, eax
0x18000e5b8  jmp     short loc_18000E5C1
0x18000e5ba  mov     rax, [rsi+10h]
0x18000e5be  sub     rax, rdx
0x18000e5c1  add     rax, rdi
0x18000e5c4  cmp     r14, rax
0x18000e5c7  jnb     short loc_18000E5DD
0x18000e5c9  test    rdx, rdx
0x18000e5cc  jnz     short loc_18000E5D2
0x18000e5ce  xor     eax, eax
0x18000e5d0  jmp     short loc_18000E5D9
0x18000e5d2  mov     rax, [rsi+10h]
0x18000e5d6  sub     rax, rdx
0x18000e5d9  lea     r14, [rax+rdi]
0x18000e5dd  mov     rcx, r14; Size
0x18000e5e0  test    r14, r14
0x18000e5e3  jz      short loc_18000E612
0x18000e5e5  xor     edx, edx
0x18000e5e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e5eb  div     r14
0x18000e5ee  cmp     rax, 1
0x18000e5f2  jnb     short loc_18000E612
0x18000e5f4  xor     edx, edx; char *
0x18000e5f6  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18000e5fb  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x18000e600  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000e607  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000e60c  call    _CxxThrowException_0
0x18000e612  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e617  mov     r15, rax
0x18000e61a  mov     [rsp+68h+arg_10], rax
0x18000e622  mov     r8, [rsi+8]; Source
0x18000e626  mov     rdx, rbx
0x18000e629  sub     rdx, r8; DestinationSize
0x18000e62c  lea     r12, [rdx+rax]
0x18000e630  jz      short loc_18000E63E
0x18000e632  mov     r9, rdx; SourceSize
0x18000e635  mov     rcx, rax; Destination
0x18000e638  call    cs:__imp_memmove_s
0x18000e63e  lea     r13, [r12+rdi]
0x18000e642  test    rdi, rdi
0x18000e645  jz      short loc_18000E656
0x18000e647  mov     r8, rdi; Size
0x18000e64a  mov     dl, byte ptr [rsp+68h+Val]; Val
0x18000e64e  mov     rcx, r12; void *
0x18000e651  call    memset_0
0x18000e656  mov     rdx, [rsi+10h]
0x18000e65a  sub     rdx, rbx; DestinationSize
0x18000e65d  jz      short loc_18000E66F
0x18000e65f  mov     r9, rdx; SourceSize
0x18000e662  mov     r8, rbx; Source
0x18000e665  mov     rcx, r13; Destination
0x18000e668  call    cs:__imp_memmove_s
0x18000e66e  nop
0x18000e66f  mov     rcx, [rsi+8]; Block
0x18000e673  test    rcx, rcx
0x18000e676  jnz     short loc_18000E67C
0x18000e678  xor     eax, eax
0x18000e67a  jmp     short loc_18000E683
0x18000e67c  mov     rax, [rsi+10h]
0x18000e680  sub     rax, rcx
0x18000e683  add     rdi, rax
0x18000e686  test    rcx, rcx
0x18000e689  jz      short loc_18000E690
0x18000e68b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e690  lea     rax, [r15+r14]
0x18000e694  mov     [rsi+18h], rax
0x18000e698  lea     rax, [r15+rdi]
0x18000e69c  mov     [rsi+10h], rax
0x18000e6a0  mov     [rsi+8], r15
0x18000e6a4  jmp     loc_18000E750
0x18000e6a9  mov     r14, [rcx+10h]
0x18000e6ad  mov     rax, r14
0x18000e6b0  sub     rax, rbx
0x18000e6b3  cmp     rax, rdi
0x18000e6b6  jnb     short loc_18000E6FA
0x18000e6b8  lea     rcx, [rbx+rdi]; Destination
0x18000e6bc  sub     r14, rbx
0x18000e6bf  jz      short loc_18000E6D5
0x18000e6c1  mov     r9, r14; SourceSize
0x18000e6c4  mov     r8, rbx; Source
0x18000e6c7  mov     rdx, r14; DestinationSize
0x18000e6ca  call    cs:__imp_memmove_s
0x18000e6d0  mov     r9b, byte ptr [rsp+68h+Val]
0x18000e6d5  mov     rcx, [rsi+10h]; void *
0x18000e6d9  mov     r8, rbx
0x18000e6dc  sub     r8, rcx
0x18000e6df  add     r8, rdi; Size
0x18000e6e2  jz      short loc_18000E6ED
0x18000e6e4  mov     dl, r9b; Val
0x18000e6e7  call    memset_0
0x18000e6ec  nop
0x18000e6ed  add     [rsi+10h], rdi
0x18000e6f1  mov     rdx, [rsi+10h]
0x18000e6f5  sub     rdx, rdi
0x18000e6f8  jmp     short loc_18000E740
0x18000e6fa  mov     r8, r14
0x18000e6fd  sub     r8, rdi; Source
0x18000e700  mov     rdx, r14
0x18000e703  sub     rdx, r8; DestinationSize
0x18000e706  lea     r15, [rdx+r14]
0x18000e70a  jz      short loc_18000E718
0x18000e70c  mov     r9, rdx; SourceSize
0x18000e70f  mov     rcx, r14; Destination
0x18000e712  call    cs:__imp_memmove_s
0x18000e718  mov     [rsi+10h], r15
0x18000e71c  mov     rdx, r14
0x18000e71f  sub     rdx, rbx
0x18000e722  sub     rdx, rdi; DestinationSize
0x18000e725  test    rdx, rdx
0x18000e728  jle     short loc_18000E73C
0x18000e72a  sub     r14, rdx
0x18000e72d  mov     r9, rdx; SourceSize
0x18000e730  mov     r8, rbx; Source
0x18000e733  mov     rcx, r14; Destination
0x18000e736  call    cs:__imp_memmove_s
0x18000e73c  lea     rdx, [rbx+rdi]
0x18000e740  lea     r8, [rsp+68h+arg_10]
0x18000e748  mov     rcx, rbx
0x18000e74b  call    ??$fill@PEAEE@std@@YAXPEAE0AEBE@Z; std::fill<uchar *,uchar>(uchar *,uchar *,uchar const &)
0x18000e750  lea     r11, [rsp+68h+var_28]
0x18000e755  mov     rbx, [r11+38h]
0x18000e759  mov     rsi, [r11+48h]
0x18000e75d  mov     rsp, r11
0x18000e760  pop     r15
0x18000e762  pop     r14
0x18000e764  pop     r13
0x18000e766  pop     r12
0x18000e768  pop     rdi
0x18000e769  retn
```
