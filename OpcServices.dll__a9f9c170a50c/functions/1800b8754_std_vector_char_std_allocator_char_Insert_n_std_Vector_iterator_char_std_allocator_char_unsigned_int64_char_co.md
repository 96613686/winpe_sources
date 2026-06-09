# std::vector<char,std::allocator<char>>::_Insert_n(std::_Vector_iterator<char,std::allocator<char>>,unsigned __int64,char const &)

- ea: `0x1800b8754`
- end: `0x1800b8952`
- name: `?_Insert_n@?$vector@DV?$allocator@D@std@@@std@@IEAAXV?$_Vector_iterator@DV?$allocator@D@std@@@2@_KAEBD@Z`
- size: `510`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800a5a40`

## callees

- `0x180060268`
- `0x18007e3e8`
- `0x180091c7c`
- `0x1800b8754`
- `0x1800cce54`
- `0x1800d5fe4`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800b884a`
- `msvcrt!memmove_s` at `0x1800b8871`
- `msvcrt!memmove_s` at `0x1800b88c7`
- `msvcrt!memmove_s` at `0x1800b88ff`
- `msvcrt!memmove_s` at `0x1800b8923`
- `msvcrt!memmove_s` at `0x1800b884a`
- `msvcrt!memmove_s` at `0x1800b8871`
- `msvcrt!memmove_s` at `0x1800b88c7`
- `msvcrt!memmove_s` at `0x1800b88ff`
- `msvcrt!memmove_s` at `0x1800b8923`

## pseudocode

```c
char *__fastcall std::vector<char>::_Insert_n(__int64 a1, _BYTE *a2, rsize_t a3, _BYTE *a4)
{
  char *result; // rax
  __int64 v7; // rsi
  __int64 v8; // rdx
  rsize_t v9; // r8
  void **v10; // r14
  unsigned __int64 v11; // rax
  char *v12; // rax
  rsize_t v13; // r12
  char *v14; // rcx
  char *v15; // rax
  char *v16; // rax
  char *v17; // r15
  _BYTE *v18; // r8
  rsize_t v19; // rdx
  char *v20; // r13
  void *v21; // rcx
  char *v22; // r15
  unsigned __int64 v23; // rsi
  size_t v24; // r15
  char *v25; // rdx
  signed __int64 v26; // rsi
  _UNKNOWN *retaddr; // [rsp+58h] [rbp+0h] BYREF
  char Val; // [rsp+60h] [rbp+8h]
  void *v29; // [rsp+70h] [rbp+18h] BYREF

  result = (char *)&retaddr;
  v7 = a1;
  LOBYTE(a1) = *a4;
  Val = *a4;
  LOBYTE(v29) = *a4;
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
      std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(a1);
    if ( v8 )
      v12 = (char *)*v10 - v8;
    else
      v12 = 0;
    try
    {
      if ( v9 >= (unsigned __int64)&v12[a3] )
      {
        v22 = (char *)*v10;
        v23 = (_BYTE *)*v10 - a2;
        if ( v23 >= a3 )
        {
          memmove_s(*v10, a3, &v22[-a3], a3);
          *v10 = &v22[a3];
          v26 = v23 - a3;
          if ( v26 > 0 )
            memmove_s(&v22[-v26], v26, a2, v26);
          v25 = &a2[a3];
        }
        else
        {
          if ( v23 )
          {
            memmove_s(&a2[a3], (_BYTE *)*v10 - a2, a2, (_BYTE *)*v10 - a2);
            LOBYTE(a1) = Val;
          }
          v24 = &a2[a3] - (_BYTE *)*v10;
          if ( v24 )
          {
            LOBYTE(v8) = a1;
            memset_0(*v10, v8, v24);
          }
          v25 = (char *)*v10;
          *v10 = (char *)*v10 + a3;
        }
        result = (char *)std::fill<unsigned char *,unsigned char>(a2, v25, &v29);
      }
      else
      {
        v13 = 0;
        if ( ~(v9 >> 1) >= v9 )
          v13 = v9 + (v9 >> 1);
        v14 = (char *)*v10;
        if ( v8 )
          v15 = &v14[-v8];
        else
          v15 = 0;
        if ( v13 < (unsigned __int64)&v15[a3] )
          v13 = a3 + ((unsigned __int64)&v14[-v8] & -(__int64)(v8 != 0));
        v16 = (char *)std::_Allocate<char>(v13, 0);
        v17 = v16;
        v29 = v16;
        v18 = *(_BYTE **)(v7 + 8);
        v19 = a2 - v18;
        v20 = &v16[a2 - v18];
        if ( a2 != v18 )
          memmove_s(v16, v19, v18, a2 - v18);
        LOBYTE(v19) = Val;
        memset_0(v20, v19, a3);
        if ( *v10 != a2 )
          memmove_s(&v20[a3], (_BYTE *)*v10 - a2, a2, (_BYTE *)*v10 - a2);
        v21 = *(void **)(v7 + 8);
        if ( v21 )
        {
          a3 = (rsize_t)*v10 + a3 - (_QWORD)v21;
          operator delete(v21);
        }
        *(_QWORD *)(v7 + 24) = &v17[v13];
        result = &v17[a3];
        *v10 = &v17[a3];
        *(_QWORD *)(v7 + 8) = v17;
      }
    }
    catch ( ... )
    {
      operator delete(v29);
      throw;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800b8754  mov     rax, rsp
0x1800b8757  push    rdi
0x1800b8758  push    r12
0x1800b875a  push    r13
0x1800b875c  push    r14
0x1800b875e  push    r15
0x1800b8760  sub     rsp, 30h
0x1800b8764  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x1800b876c  mov     [rax+10h], rbx
0x1800b8770  mov     [rax+20h], rsi
0x1800b8774  mov     rdi, r8
0x1800b8777  mov     rbx, rdx
0x1800b877a  mov     rsi, rcx
0x1800b877d  mov     cl, [r9]
0x1800b8780  mov     [rax+8], cl
0x1800b8783  mov     [rax+18h], cl
0x1800b8786  mov     rdx, [rsi+8]
0x1800b878a  test    rdx, rdx
0x1800b878d  jnz     short loc_1800B8794
0x1800b878f  xor     r8d, r8d
0x1800b8792  jmp     short loc_1800B879B
0x1800b8794  mov     r8, [rsi+18h]
0x1800b8798  sub     r8, rdx
0x1800b879b  test    rdi, rdi
0x1800b879e  jz      loc_1800B893A
0x1800b87a4  lea     r14, [rsi+10h]
0x1800b87a8  test    rdx, rdx
0x1800b87ab  jnz     short loc_1800B87B1
0x1800b87ad  xor     eax, eax
0x1800b87af  jmp     short loc_1800B87B7
0x1800b87b1  mov     rax, [r14]
0x1800b87b4  sub     rax, rdx
0x1800b87b7  not     rax
0x1800b87ba  cmp     rax, rdi
0x1800b87bd  jnb     short loc_1800B87C5
0x1800b87bf  call    ?_Xlen@?$vector@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@V?$allocator@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@@3@@std@@KAXXZ; std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(void)
0x1800b87c5  test    rdx, rdx
0x1800b87c8  jnz     short loc_1800B87CE
0x1800b87ca  xor     eax, eax
0x1800b87cc  jmp     short loc_1800B87D4
0x1800b87ce  mov     rax, [r14]
0x1800b87d1  sub     rax, rdx
0x1800b87d4  add     rax, rdi
0x1800b87d7  cmp     r8, rax
0x1800b87da  jnb     loc_1800B88A4
0x1800b87e0  mov     rax, r8
0x1800b87e3  shr     rax, 1
0x1800b87e6  mov     rcx, rax
0x1800b87e9  not     rcx
0x1800b87ec  add     rax, r8
0x1800b87ef  xor     r12d, r12d
0x1800b87f2  cmp     rcx, r8
0x1800b87f5  cmovnb  r12, rax
0x1800b87f9  mov     rcx, [r14]
0x1800b87fc  test    rdx, rdx
0x1800b87ff  jnz     short loc_1800B8805
0x1800b8801  xor     eax, eax
0x1800b8803  jmp     short loc_1800B880B
0x1800b8805  mov     rax, rcx
0x1800b8808  sub     rax, rdx
0x1800b880b  add     rax, rdi
0x1800b880e  cmp     r12, rax
0x1800b8811  jnb     short loc_1800B8822
0x1800b8813  sub     rcx, rdx
0x1800b8816  neg     rdx
0x1800b8819  sbb     r12, r12
0x1800b881c  and     r12, rcx
0x1800b881f  add     r12, rdi
0x1800b8822  xor     edx, edx
0x1800b8824  mov     rcx, r12
0x1800b8827  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x1800b882c  mov     r15, rax
0x1800b882f  mov     [rsp+58h+arg_10], rax
0x1800b8834  mov     r8, [rsi+8]; Source
0x1800b8838  mov     rdx, rbx
0x1800b883b  sub     rdx, r8; DestinationSize
0x1800b883e  lea     r13, [rdx+rax]
0x1800b8842  jz      short loc_1800B8850
0x1800b8844  mov     r9, rdx; SourceSize
0x1800b8847  mov     rcx, rax; Destination
0x1800b884a  call    cs:__imp_memmove_s
0x1800b8850  mov     r8, rdi; Size
0x1800b8853  mov     dl, byte ptr [rsp+58h+Val]; Val
0x1800b8857  mov     rcx, r13; void *
0x1800b885a  call    memset_0
0x1800b885f  mov     rdx, [r14]
0x1800b8862  sub     rdx, rbx; DestinationSize
0x1800b8865  jz      short loc_1800B8878
0x1800b8867  lea     rcx, [rdi+r13]; Destination
0x1800b886b  mov     r9, rdx; SourceSize
0x1800b886e  mov     r8, rbx; Source
0x1800b8871  call    cs:__imp_memmove_s
0x1800b8877  nop
0x1800b8878  mov     rcx, [rsi+8]; Block
0x1800b887c  test    rcx, rcx
0x1800b887f  jz      short loc_1800B888C
0x1800b8881  sub     rdi, rcx
0x1800b8884  add     rdi, [r14]
0x1800b8887  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b888c  lea     rax, [r15+r12]
0x1800b8890  mov     [rsi+18h], rax
0x1800b8894  lea     rax, [rdi+r15]
0x1800b8898  mov     [r14], rax
0x1800b889b  mov     [rsi+8], r15
0x1800b889f  jmp     loc_1800B893A
0x1800b88a4  mov     r15, [r14]
0x1800b88a7  mov     rsi, r15
0x1800b88aa  sub     rsi, rbx
0x1800b88ad  cmp     rsi, rdi
0x1800b88b0  jnb     short loc_1800B88F0
0x1800b88b2  lea     r15, [rbx+rdi]
0x1800b88b6  test    rsi, rsi
0x1800b88b9  jz      short loc_1800B88D1
0x1800b88bb  mov     r9, rsi; SourceSize
0x1800b88be  mov     r8, rbx; Source
0x1800b88c1  mov     rdx, rsi; DestinationSize
0x1800b88c4  mov     rcx, r15; Destination
0x1800b88c7  call    cs:__imp_memmove_s
0x1800b88cd  mov     cl, byte ptr [rsp+58h+Val]
0x1800b88d1  sub     r15, [r14]
0x1800b88d4  jz      short loc_1800B88E4
0x1800b88d6  mov     r8, r15; Size
0x1800b88d9  mov     dl, cl; Val
0x1800b88db  mov     rcx, [r14]; void *
0x1800b88de  call    memset_0
0x1800b88e3  nop
0x1800b88e4  mov     rdx, [r14]
0x1800b88e7  lea     rax, [rdx+rdi]
0x1800b88eb  mov     [r14], rax
0x1800b88ee  jmp     short loc_1800B892D
0x1800b88f0  mov     r8, r15
0x1800b88f3  sub     r8, rdi; Source
0x1800b88f6  mov     r9, rdi; SourceSize
0x1800b88f9  mov     rdx, rdi; DestinationSize
0x1800b88fc  mov     rcx, r15; Destination
0x1800b88ff  call    cs:__imp_memmove_s
0x1800b8905  lea     rax, [r15+rdi]
0x1800b8909  mov     [r14], rax
0x1800b890c  sub     rsi, rdi
0x1800b890f  test    rsi, rsi
0x1800b8912  jle     short loc_1800B8929
0x1800b8914  sub     r15, rsi
0x1800b8917  mov     r9, rsi; SourceSize
0x1800b891a  mov     r8, rbx; Source
0x1800b891d  mov     rdx, rsi; DestinationSize
0x1800b8920  mov     rcx, r15; Destination
0x1800b8923  call    cs:__imp_memmove_s
0x1800b8929  lea     rdx, [rbx+rdi]
0x1800b892d  lea     r8, [rsp+58h+arg_10]
0x1800b8932  mov     rcx, rbx
0x1800b8935  call    ??$fill@PEAEE@std@@YAXPEAE0AEBE@Z; std::fill<uchar *,uchar>(uchar *,uchar *,uchar const &)
0x1800b893a  mov     rbx, [rsp+58h+arg_8]
0x1800b893f  mov     rsi, [rsp+58h+arg_18]
0x1800b8944  add     rsp, 30h
0x1800b8948  pop     r15
0x1800b894a  pop     r14
0x1800b894c  pop     r13
0x1800b894e  pop     r12
0x1800b8950  pop     rdi
0x1800b8951  retn
```
