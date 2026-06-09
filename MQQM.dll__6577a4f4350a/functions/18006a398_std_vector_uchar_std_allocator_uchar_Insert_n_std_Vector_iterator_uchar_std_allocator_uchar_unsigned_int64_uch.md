# std::vector<uchar,std::allocator<uchar>>::_Insert_n(std::_Vector_iterator<uchar,std::allocator<uchar>>,unsigned __int64,uchar const &)

- ea: `0x18006a398`
- end: `0x18006a5ea`
- name: `?_Insert_n@?$vector@EV?$allocator@E@std@@@std@@IEAAXV?$_Vector_iterator@EV?$allocator@E@std@@@2@_KAEBE@Z`
- size: `594`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18006a718`

## callees

- `0x180004d91`
- `0x1800111d0`
- `0x180064830`
- `0x18006a398`
- `0x18009bd1c`
- `0x1800d6e56`

## import_xrefs

- `msvcrt!free` at `0x18006a518`
- `msvcrt!free` at `0x18006a518`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18006a489`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18006a489`
- `msvcrt!memmove_s` at `0x18006a4d5`
- `msvcrt!memmove_s` at `0x18006a4ff`
- `msvcrt!memmove_s` at `0x18006a55a`
- `msvcrt!memmove_s` at `0x18006a592`
- `msvcrt!memmove_s` at `0x18006a5b6`
- `msvcrt!memmove_s` at `0x18006a4d5`
- `msvcrt!memmove_s` at `0x18006a4ff`
- `msvcrt!memmove_s` at `0x18006a55a`
- `msvcrt!memmove_s` at `0x18006a592`
- `msvcrt!memmove_s` at `0x18006a5b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall std::vector<unsigned char>::_Insert_n(__int64 a1, _BYTE *a2, rsize_t a3, _BYTE *a4)
{
  char *result; // rax
  __int64 v7; // r13
  __int64 v8; // rdx
  rsize_t v9; // r8
  void **v10; // r14
  unsigned __int64 v11; // rax
  char *v12; // rax
  unsigned __int64 v13; // rsi
  char *v14; // rax
  char *v15; // rax
  unsigned __int64 v16; // rcx
  char *v17; // rax
  int v18; // edx
  char *v19; // r15
  _BYTE *v20; // r8
  signed __int64 v21; // r12
  char *v22; // r12
  _BYTE *v23; // rcx
  char *v24; // r15
  unsigned __int64 v25; // rsi
  size_t v26; // r15
  char *v27; // rdx
  signed __int64 v28; // rsi
  _QWORD pExceptionObject[4]; // [rsp+20h] [rbp-48h] BYREF
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h] BYREF
  const char *Val; // [rsp+70h] [rbp+8h] BYREF
  char *v32; // [rsp+80h] [rbp+18h] BYREF

  result = (char *)&retaddr;
  v7 = a1;
  LOBYTE(Val) = *a4;
  LOBYTE(a1) = (_BYTE)Val;
  LOBYTE(v32) = (_BYTE)Val;
  v8 = *(_QWORD *)(v7 + 8);
  if ( v8 )
    v9 = *(_QWORD *)(v7 + 24) - v8;
  else
    v9 = 0;
  if ( a3 )
  {
    v10 = (void **)(v7 + 16);
    if ( v8 )
      v11 = (unsigned __int64)*v10 - v8;
    else
      v11 = 0;
    if ( ~v11 < a3 )
      std::vector<CAttachment>::_Xlen(a1, v8, v9);
    if ( v8 )
      v12 = (char *)*v10 - v8;
    else
      v12 = 0;
    if ( v9 >= (unsigned __int64)&v12[a3] )
    {
      v24 = (char *)*v10;
      v25 = (_BYTE *)*v10 - a2;
      if ( v25 >= a3 )
      {
        memmove_s(*v10, a3, &v24[-a3], a3);
        *v10 = &v24[a3];
        v28 = v25 - a3;
        if ( v28 > 0 )
          memmove_s(&v24[-v28], v28, a2, v28);
        v27 = &a2[a3];
      }
      else
      {
        if ( v25 )
        {
          memmove_s(&a2[a3], (_BYTE *)*v10 - a2, a2, (_BYTE *)*v10 - a2);
          LOBYTE(a1) = (_BYTE)Val;
        }
        v26 = &a2[a3] - (_BYTE *)*v10;
        if ( v26 )
        {
          LOBYTE(v8) = a1;
          memset_0(*v10, v8, v26);
        }
        v27 = (char *)*v10;
        *v10 = (char *)*v10 + a3;
      }
      return (char *)std::fill<unsigned char *,unsigned char>(a2, v27, &v32);
    }
    else
    {
      v13 = 0;
      if ( ~(v9 >> 1) >= v9 )
        v13 = v9 + (v9 >> 1);
      if ( v8 )
        v14 = (char *)*v10 - v8;
      else
        v14 = 0;
      if ( v13 < (unsigned __int64)&v14[a3] )
      {
        if ( v8 )
          v15 = (char *)*v10 - v8;
        else
          v15 = 0;
        v13 = (unsigned __int64)&v15[a3];
      }
      if ( v13 )
      {
        if ( !(0xFFFFFFFFFFFFFFFFuLL / v13) )
        {
          Val = 0;
          exception::exception((exception *)pExceptionObject, &Val);
          pExceptionObject[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)pExceptionObject;
        }
        v16 = v13;
      }
      else
      {
        v16 = 0;
      }
      v17 = (char *)MmAllocate(v16);
      v19 = v17;
      v32 = v17;
      try
      {
        v20 = *(_BYTE **)(v7 + 8);
        v21 = a2 - v20;
        if ( a2 != v20 )
          memmove_s(v17, a2 - v20, v20, a2 - v20);
        v22 = &v19[v21];
        LOBYTE(v18) = (_BYTE)Val;
        memset_0(v22, v18, a3);
        if ( *v10 != a2 )
          memmove_s(&v22[a3], (_BYTE *)*v10 - a2, a2, (_BYTE *)*v10 - a2);
      }
      catch ( ... )
      {
        free(v32);
        throw;
      }
      v23 = *(_BYTE **)(v7 + 8);
      if ( v23 )
      {
        a3 += (_BYTE *)*v10 - v23;
        free(v23);
      }
      *(_QWORD *)(v7 + 24) = &v19[v13];
      result = &v19[a3];
      *v10 = &v19[a3];
      *(_QWORD *)(v7 + 8) = v19;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006a398  mov     rax, rsp
0x18006a39b  mov     [rax+10h], rbx
0x18006a39f  mov     [rax+20h], rsi
0x18006a3a3  push    rdi
0x18006a3a4  push    r12
0x18006a3a6  push    r13
0x18006a3a8  push    r14
0x18006a3aa  push    r15
0x18006a3ac  sub     rsp, 40h
0x18006a3b0  mov     rdi, r8
0x18006a3b3  mov     rbx, rdx
0x18006a3b6  mov     r13, rcx
0x18006a3b9  mov     cl, [r9]
0x18006a3bc  mov     [rax+8], cl
0x18006a3bf  mov     [rax+18h], cl
0x18006a3c2  mov     rdx, [r13+8]
0x18006a3c6  test    rdx, rdx
0x18006a3c9  jnz     short loc_18006A3D0
0x18006a3cb  xor     r8d, r8d
0x18006a3ce  jmp     short loc_18006A3D7
0x18006a3d0  mov     r8, [r13+18h]
0x18006a3d4  sub     r8, rdx
0x18006a3d7  test    rdi, rdi
0x18006a3da  jz      loc_18006A5D0
0x18006a3e0  lea     r14, [r13+10h]
0x18006a3e4  test    rdx, rdx
0x18006a3e7  jnz     short loc_18006A3ED
0x18006a3e9  xor     eax, eax
0x18006a3eb  jmp     short loc_18006A3F3
0x18006a3ed  mov     rax, [r14]
0x18006a3f0  sub     rax, rdx
0x18006a3f3  not     rax
0x18006a3f6  cmp     rax, rdi
0x18006a3f9  jnb     short loc_18006A401
0x18006a3fb  call    ?_Xlen@?$vector@VCAttachment@@V?$allocator@VCAttachment@@@std@@@std@@KAXXZ; std::vector<CAttachment>::_Xlen(void)
0x18006a401  test    rdx, rdx
0x18006a404  jnz     short loc_18006A40A
0x18006a406  xor     eax, eax
0x18006a408  jmp     short loc_18006A410
0x18006a40a  mov     rax, [r14]
0x18006a40d  sub     rax, rdx
0x18006a410  add     rax, rdi
0x18006a413  cmp     r8, rax
0x18006a416  jnb     loc_18006A537
0x18006a41c  mov     rax, r8
0x18006a41f  shr     rax, 1
0x18006a422  mov     rcx, rax
0x18006a425  not     rcx
0x18006a428  add     rax, r8
0x18006a42b  xor     esi, esi
0x18006a42d  cmp     rcx, r8
0x18006a430  cmovnb  rsi, rax
0x18006a434  test    rdx, rdx
0x18006a437  jnz     short loc_18006A43D
0x18006a439  xor     eax, eax
0x18006a43b  jmp     short loc_18006A443
0x18006a43d  mov     rax, [r14]
0x18006a440  sub     rax, rdx
0x18006a443  add     rax, rdi
0x18006a446  cmp     rsi, rax
0x18006a449  jnb     short loc_18006A45E
0x18006a44b  test    rdx, rdx
0x18006a44e  jnz     short loc_18006A454
0x18006a450  xor     eax, eax
0x18006a452  jmp     short loc_18006A45A
0x18006a454  mov     rax, [r14]
0x18006a457  sub     rax, rdx
0x18006a45a  lea     rsi, [rax+rdi]
0x18006a45e  test    rsi, rsi
0x18006a461  jnz     short loc_18006A467
0x18006a463  xor     ecx, ecx
0x18006a465  jmp     short loc_18006A4B0
0x18006a467  xor     edx, edx
0x18006a469  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006a46d  div     rsi
0x18006a470  cmp     rax, 1
0x18006a474  jnb     short loc_18006A4AD
0x18006a476  mov     [rsp+68h+Val], 0
0x18006a47f  lea     rdx, [rsp+68h+Val]
0x18006a484  lea     rcx, [rsp+68h+pExceptionObject]
0x18006a489  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18006a48f  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18006a496  mov     [rsp+68h+pExceptionObject], rax
0x18006a49b  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18006a4a2  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18006a4a7  call    _CxxThrowException_0
0x18006a4ad  mov     rcx, rsi; unsigned __int64
0x18006a4b0  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18006a4b5  mov     r15, rax
0x18006a4b8  mov     [rsp+68h+arg_10], rax
0x18006a4c0  mov     r8, [r13+8]; Source
0x18006a4c4  mov     r12, rbx
0x18006a4c7  sub     r12, r8
0x18006a4ca  jz      short loc_18006A4DB
0x18006a4cc  mov     r9, r12; SourceSize
0x18006a4cf  mov     rdx, r12; DestinationSize
0x18006a4d2  mov     rcx, rax; Destination
0x18006a4d5  call    cs:__imp_memmove_s
0x18006a4db  add     r12, r15
0x18006a4de  mov     r8, rdi; Size
0x18006a4e1  mov     dl, byte ptr [rsp+68h+Val]; Val
0x18006a4e5  mov     rcx, r12; void *
0x18006a4e8  call    memset_0
0x18006a4ed  mov     rdx, [r14]
0x18006a4f0  sub     rdx, rbx; DestinationSize
0x18006a4f3  jz      short loc_18006A506
0x18006a4f5  lea     rcx, [r12+rdi]; Destination
0x18006a4f9  mov     r9, rdx; SourceSize
0x18006a4fc  mov     r8, rbx; Source
0x18006a4ff  call    cs:__imp_memmove_s
0x18006a505  nop
0x18006a506  mov     rcx, [r13+8]; Block
0x18006a50a  test    rcx, rcx
0x18006a50d  jz      short loc_18006A51F
0x18006a50f  mov     rax, [r14]
0x18006a512  sub     rax, rcx
0x18006a515  add     rdi, rax
0x18006a518  call    cs:__imp_free
0x18006a51e  nop
0x18006a51f  lea     rax, [r15+rsi]
0x18006a523  mov     [r13+18h], rax
0x18006a527  lea     rax, [rdi+r15]
0x18006a52b  mov     [r14], rax
0x18006a52e  mov     [r13+8], r15
0x18006a532  jmp     loc_18006A5D0
0x18006a537  mov     r15, [r14]
0x18006a53a  mov     rsi, r15
0x18006a53d  sub     rsi, rbx
0x18006a540  cmp     rsi, rdi
0x18006a543  jnb     short loc_18006A583
0x18006a545  lea     r15, [rbx+rdi]
0x18006a549  test    rsi, rsi
0x18006a54c  jz      short loc_18006A564
0x18006a54e  mov     r9, rsi; SourceSize
0x18006a551  mov     r8, rbx; Source
0x18006a554  mov     rdx, rsi; DestinationSize
0x18006a557  mov     rcx, r15; Destination
0x18006a55a  call    cs:__imp_memmove_s
0x18006a560  mov     cl, byte ptr [rsp+68h+Val]
0x18006a564  sub     r15, [r14]
0x18006a567  jz      short loc_18006A577
0x18006a569  mov     r8, r15; Size
0x18006a56c  mov     dl, cl; Val
0x18006a56e  mov     rcx, [r14]; void *
0x18006a571  call    memset_0
0x18006a576  nop
0x18006a577  mov     rdx, [r14]
0x18006a57a  lea     rax, [rdx+rdi]
0x18006a57e  mov     [r14], rax
0x18006a581  jmp     short loc_18006A5C0
0x18006a583  mov     r8, r15
0x18006a586  sub     r8, rdi; Source
0x18006a589  mov     r9, rdi; SourceSize
0x18006a58c  mov     rdx, rdi; DestinationSize
0x18006a58f  mov     rcx, r15; Destination
0x18006a592  call    cs:__imp_memmove_s
0x18006a598  lea     rax, [r15+rdi]
0x18006a59c  mov     [r14], rax
0x18006a59f  sub     rsi, rdi
0x18006a5a2  test    rsi, rsi
0x18006a5a5  jle     short loc_18006A5BC
0x18006a5a7  sub     r15, rsi
0x18006a5aa  mov     r9, rsi; SourceSize
0x18006a5ad  mov     r8, rbx; Source
0x18006a5b0  mov     rdx, rsi; DestinationSize
0x18006a5b3  mov     rcx, r15; Destination
0x18006a5b6  call    cs:__imp_memmove_s
0x18006a5bc  lea     rdx, [rbx+rdi]
0x18006a5c0  lea     r8, [rsp+68h+arg_10]
0x18006a5c8  mov     rcx, rbx
0x18006a5cb  call    ??$fill@PEAEE@std@@YAXPEAE0AEBE@Z; std::fill<uchar *,uchar>(uchar *,uchar *,uchar const &)
0x18006a5d0  lea     r11, [rsp+68h+var_28]
0x18006a5d5  mov     rbx, [r11+38h]
0x18006a5d9  mov     rsi, [r11+48h]
0x18006a5dd  mov     rsp, r11
0x18006a5e0  pop     r15
0x18006a5e2  pop     r14
0x18006a5e4  pop     r13
0x18006a5e6  pop     r12
0x18006a5e8  pop     rdi
0x18006a5e9  retn
```
