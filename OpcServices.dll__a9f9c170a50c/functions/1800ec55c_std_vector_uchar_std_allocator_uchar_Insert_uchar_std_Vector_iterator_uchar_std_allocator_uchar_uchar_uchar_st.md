# std::vector<uchar,std::allocator<uchar>>::_Insert<uchar *>(std::_Vector_iterator<uchar,std::allocator<uchar>>,uchar *,uchar *,std::forward_iterator_tag)

- ea: `0x1800ec55c`
- end: `0x1800ec7b5`
- name: `??$_Insert@PEAE@?$vector@EV?$allocator@E@std@@@std@@QEAAXV?$_Vector_iterator@EV?$allocator@E@std@@@1@PEAE1Uforward_iterator_tag@1@@Z`
- size: `601`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800c2394`
- `0x1800ec504`

## callees

- `0x180060268`
- `0x1800786c0`
- `0x1800b377c`
- `0x1800cce08`
- `0x1800cce54`
- `0x1800cd38c`
- `0x1800ec55c`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800ec6ab`
- `msvcrt!memmove_s` at `0x1800ec6c2`
- `msvcrt!memmove_s` at `0x1800ec6da`
- `msvcrt!memmove_s` at `0x1800ec731`
- `msvcrt!memmove_s` at `0x1800ec751`
- `msvcrt!memmove_s` at `0x1800ec76f`
- `msvcrt!memmove_s` at `0x1800ec6ab`
- `msvcrt!memmove_s` at `0x1800ec6c2`
- `msvcrt!memmove_s` at `0x1800ec6da`
- `msvcrt!memmove_s` at `0x1800ec731`
- `msvcrt!memmove_s` at `0x1800ec751`
- `msvcrt!memmove_s` at `0x1800ec76f`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1800ec661`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1800ec661`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall std::vector<unsigned char>::_Insert<unsigned char *>(__int64 a1, _BYTE *a2, char *a3, __int64 a4)
{
  char *result; // rax
  rsize_t v9; // rdi
  __int64 v10; // rdx
  unsigned __int64 v11; // r10
  void **v12; // rsi
  unsigned __int64 v13; // rax
  char *v14; // rax
  size_t v15; // r14
  char *v16; // rax
  char *v17; // rax
  size_t v18; // rcx
  char *v19; // rax
  char *v20; // r15
  _BYTE *v21; // r8
  char *v22; // r12
  _BYTE *v23; // rcx
  signed __int64 v24; // rbx
  char *v25; // r15
  rsize_t v26; // rdx
  rsize_t v27; // r14
  _QWORD pExceptionObject[3]; // [rsp+28h] [rbp-40h] BYREF
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h] BYREF
  void *v30; // [rsp+70h] [rbp+8h]
  void *Source; // [rsp+80h] [rbp+18h] BYREF

  result = (char *)&retaddr;
  Source = a3;
  v9 = a4 - (_QWORD)a3;
  v10 = *(_QWORD *)(a1 + 8);
  if ( v10 )
    v11 = *(_QWORD *)(a1 + 24) - v10;
  else
    v11 = 0;
  if ( v9 )
  {
    v12 = (void **)(a1 + 16);
    if ( v10 )
      v13 = (unsigned __int64)*v12 - v10;
    else
      v13 = 0;
    if ( ~v13 < v9 )
      std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(a1);
    if ( v10 )
      v14 = (char *)*v12 - v10;
    else
      v14 = 0;
    if ( v11 >= (unsigned __int64)&v14[v9] )
    {
      v25 = (char *)*v12;
      v26 = (_BYTE *)*v12 - a2;
      if ( v26 >= v9 )
      {
        memmove_s(*v12, v9, &v25[-v9], v9);
        *v12 = &v25[v9];
        std::copy_backward<unsigned char *,unsigned char *>(a2);
      }
      else
      {
        if ( v26 )
          memmove_s(&a2[v9], v26, a2, (_BYTE *)*v12 - a2);
        v27 = a4 - (_QWORD)&a3[(_BYTE *)*v12 - a2];
        if ( v27 )
          memmove_s(*v12, v27, &a3[(_BYTE *)*v12 - a2], v27);
        *v12 = (char *)*v12 + v9;
      }
      return (char *)std::copy<unsigned char const *,unsigned char *>(a3);
    }
    else
    {
      if ( ~(v11 >> 1) >= v11 )
        v15 = (v11 >> 1) + v11;
      else
        v15 = 0;
      if ( v10 )
        v16 = (char *)*v12 - v10;
      else
        v16 = 0;
      if ( v15 < (unsigned __int64)&v16[v9] )
      {
        if ( v10 )
          v17 = (char *)*v12 - v10;
        else
          v17 = 0;
        v15 = (size_t)&v17[v9];
      }
      if ( v15 )
      {
        if ( !(0xFFFFFFFFFFFFFFFFuLL / v15) )
        {
          Source = 0;
          exception::exception((exception *)pExceptionObject, (const char *const *)&Source);
          pExceptionObject[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)pExceptionObject;
        }
        v18 = v15;
      }
      else
      {
        v18 = 0;
      }
      v19 = (char *)operator new(v18);
      v20 = v19;
      v30 = v19;
      try
      {
        v21 = *(_BYTE **)(a1 + 8);
        v22 = &v19[a2 - v21];
        if ( a2 != v21 )
          memmove_s(v19, a2 - v21, v21, a2 - v21);
        memmove_s(v22, v9, Source, v9);
        if ( *v12 != a2 )
          memmove_s(&v22[v9], (_BYTE *)*v12 - a2, a2, (_BYTE *)*v12 - a2);
        v23 = *(_BYTE **)(a1 + 8);
        if ( v23 )
        {
          v24 = (_BYTE *)*v12 - v23;
          operator delete(v23);
        }
        else
        {
          v24 = 0;
        }
        *(_QWORD *)(a1 + 24) = &v20[v15];
        result = &v20[v9 + v24];
        *v12 = result;
        *(_QWORD *)(a1 + 8) = v20;
      }
      catch ( ... )
      {
        operator delete(v30);
        throw;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800ec55c  mov     rax, rsp
0x1800ec55f  mov     [rax+18h], r8
0x1800ec563  push    rdi
0x1800ec564  push    r12
0x1800ec566  push    r13
0x1800ec568  push    r14
0x1800ec56a  push    r15
0x1800ec56c  sub     rsp, 40h
0x1800ec570  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1800ec578  mov     [rax+10h], rbx
0x1800ec57c  mov     [rax+20h], rsi
0x1800ec580  mov     r14, r9
0x1800ec583  mov     r12, r8
0x1800ec586  mov     rbx, rdx
0x1800ec589  mov     r13, rcx
0x1800ec58c  mov     rdi, r9
0x1800ec58f  sub     rdi, r8
0x1800ec592  mov     rdx, [rcx+8]
0x1800ec596  test    rdx, rdx
0x1800ec599  jnz     short loc_1800EC5A0
0x1800ec59b  xor     r10d, r10d
0x1800ec59e  jmp     short loc_1800EC5A7
0x1800ec5a0  mov     r10, [rcx+18h]
0x1800ec5a4  sub     r10, rdx
0x1800ec5a7  test    rdi, rdi
0x1800ec5aa  jz      loc_1800EC79B
0x1800ec5b0  lea     rsi, [rcx+10h]
0x1800ec5b4  test    rdx, rdx
0x1800ec5b7  jnz     short loc_1800EC5BD
0x1800ec5b9  xor     eax, eax
0x1800ec5bb  jmp     short loc_1800EC5C3
0x1800ec5bd  mov     rax, [rsi]
0x1800ec5c0  sub     rax, rdx
0x1800ec5c3  not     rax
0x1800ec5c6  cmp     rax, rdi
0x1800ec5c9  jnb     short loc_1800EC5D1
0x1800ec5cb  call    ?_Xlen@?$vector@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@V?$allocator@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@@3@@std@@KAXXZ; std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(void)
0x1800ec5d1  test    rdx, rdx
0x1800ec5d4  jnz     short loc_1800EC5DA
0x1800ec5d6  xor     eax, eax
0x1800ec5d8  jmp     short loc_1800EC5E0
0x1800ec5da  mov     rax, [rsi]
0x1800ec5dd  sub     rax, rdx
0x1800ec5e0  add     rax, rdi
0x1800ec5e3  cmp     r10, rax
0x1800ec5e6  jnb     loc_1800EC714
0x1800ec5ec  mov     rcx, r10
0x1800ec5ef  shr     rcx, 1
0x1800ec5f2  mov     rax, rcx
0x1800ec5f5  not     rax
0x1800ec5f8  cmp     rax, r10
0x1800ec5fb  jnb     short loc_1800EC602
0x1800ec5fd  xor     r14d, r14d
0x1800ec600  jmp     short loc_1800EC606
0x1800ec602  lea     r14, [rcx+r10]
0x1800ec606  test    rdx, rdx
0x1800ec609  jnz     short loc_1800EC60F
0x1800ec60b  xor     eax, eax
0x1800ec60d  jmp     short loc_1800EC615
0x1800ec60f  mov     rax, [rsi]
0x1800ec612  sub     rax, rdx
0x1800ec615  add     rax, rdi
0x1800ec618  cmp     r14, rax
0x1800ec61b  jnb     short loc_1800EC630
0x1800ec61d  test    rdx, rdx
0x1800ec620  jnz     short loc_1800EC626
0x1800ec622  xor     eax, eax
0x1800ec624  jmp     short loc_1800EC62C
0x1800ec626  mov     rax, [rsi]
0x1800ec629  sub     rax, rdx
0x1800ec62c  lea     r14, [rdi+rax]
0x1800ec630  test    r14, r14
0x1800ec633  jnz     short loc_1800EC639
0x1800ec635  xor     ecx, ecx
0x1800ec637  jmp     short loc_1800EC688
0x1800ec639  xor     edx, edx
0x1800ec63b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ec63f  div     r14
0x1800ec642  cmp     rax, 1
0x1800ec646  jnb     short loc_1800EC685
0x1800ec648  mov     [rsp+68h+Source], 0
0x1800ec654  lea     rdx, [rsp+68h+Source]
0x1800ec65c  lea     rcx, [rsp+68h+pExceptionObject]
0x1800ec661  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x1800ec667  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800ec66e  mov     [rsp+68h+pExceptionObject], rax
0x1800ec673  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800ec67a  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800ec67f  call    _CxxThrowException_0
0x1800ec685  mov     rcx, r14; Size
0x1800ec688  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ec68d  mov     r15, rax
0x1800ec690  mov     [rsp+68h+arg_0], rax
0x1800ec695  mov     r8, [r13+8]; Source
0x1800ec699  mov     rdx, rbx
0x1800ec69c  sub     rdx, r8; DestinationSize
0x1800ec69f  lea     r12, [rdx+rax]
0x1800ec6a3  jz      short loc_1800EC6B1
0x1800ec6a5  mov     r9, rdx; SourceSize
0x1800ec6a8  mov     rcx, rax; Destination
0x1800ec6ab  call    cs:__imp_memmove_s
0x1800ec6b1  mov     r9, rdi; SourceSize
0x1800ec6b4  mov     r8, [rsp+68h+Source]; Source
0x1800ec6bc  mov     rdx, rdi; DestinationSize
0x1800ec6bf  mov     rcx, r12; Destination
0x1800ec6c2  call    cs:__imp_memmove_s
0x1800ec6c8  mov     rdx, [rsi]
0x1800ec6cb  sub     rdx, rbx; DestinationSize
0x1800ec6ce  jz      short loc_1800EC6E1
0x1800ec6d0  lea     rcx, [r12+rdi]; Destination
0x1800ec6d4  mov     r9, rdx; SourceSize
0x1800ec6d7  mov     r8, rbx; Source
0x1800ec6da  call    cs:__imp_memmove_s
0x1800ec6e0  nop
0x1800ec6e1  mov     rcx, [r13+8]; Block
0x1800ec6e5  test    rcx, rcx
0x1800ec6e8  jnz     short loc_1800EC6EE
0x1800ec6ea  xor     ebx, ebx
0x1800ec6ec  jmp     short loc_1800EC6F9
0x1800ec6ee  mov     rbx, [rsi]
0x1800ec6f1  sub     rbx, rcx
0x1800ec6f4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ec6f9  lea     rax, [r15+r14]
0x1800ec6fd  mov     [r13+18h], rax
0x1800ec701  lea     rax, [rdi+rbx]
0x1800ec705  add     rax, r15
0x1800ec708  mov     [rsi], rax
0x1800ec70b  mov     [r13+8], r15
0x1800ec70f  jmp     loc_1800EC79B
0x1800ec714  mov     r15, [rsi]
0x1800ec717  mov     rdx, r15
0x1800ec71a  sub     rdx, rbx; DestinationSize
0x1800ec71d  cmp     rdx, rdi
0x1800ec720  jnb     short loc_1800EC760
0x1800ec722  test    rdx, rdx
0x1800ec725  jz      short loc_1800EC737
0x1800ec727  lea     rcx, [rdi+rbx]; Destination
0x1800ec72b  mov     r9, rdx; SourceSize
0x1800ec72e  mov     r8, rbx; Source
0x1800ec731  call    cs:__imp_memmove_s
0x1800ec737  mov     r15, [rsi]
0x1800ec73a  sub     r15, rbx
0x1800ec73d  add     r15, r12
0x1800ec740  sub     r14, r15
0x1800ec743  jz      short loc_1800EC758
0x1800ec745  mov     r9, r14; SourceSize
0x1800ec748  mov     r8, r15; Source
0x1800ec74b  mov     rdx, r14; DestinationSize
0x1800ec74e  mov     rcx, [rsi]; Destination
0x1800ec751  call    cs:__imp_memmove_s
0x1800ec757  nop
0x1800ec758  add     [rsi], rdi
0x1800ec75b  mov     rdx, r15
0x1800ec75e  jmp     short loc_1800EC790
0x1800ec760  mov     r8, r15
0x1800ec763  sub     r8, rdi; Source
0x1800ec766  mov     r9, rdi; SourceSize
0x1800ec769  mov     rdx, rdi; DestinationSize
0x1800ec76c  mov     rcx, r15; Destination
0x1800ec76f  call    cs:__imp_memmove_s
0x1800ec775  lea     rax, [rdi+r15]
0x1800ec779  mov     [rsi], rax
0x1800ec77c  mov     rdx, r15
0x1800ec77f  sub     rdx, rdi
0x1800ec782  mov     r8, r15
0x1800ec785  mov     rcx, rbx; Source
0x1800ec788  call    ??$copy_backward@PEAEPEAE@std@@YAPEAEPEAE00@Z; std::copy_backward<uchar *,uchar *>(uchar *,uchar *,uchar *)
0x1800ec78d  mov     rdx, r14
0x1800ec790  mov     r8, rbx
0x1800ec793  mov     rcx, r12; Source
0x1800ec796  call    ??$copy@PEBEPEAE@std@@YAPEAEPEBE0PEAE@Z; std::copy<uchar const *,uchar *>(uchar const *,uchar const *,uchar *)
0x1800ec79b  lea     r11, [rsp+68h+var_28]
0x1800ec7a0  mov     rbx, [r11+38h]
0x1800ec7a4  mov     rsi, [r11+48h]
0x1800ec7a8  mov     rsp, r11
0x1800ec7ab  pop     r15
0x1800ec7ad  pop     r14
0x1800ec7af  pop     r13
0x1800ec7b1  pop     r12
0x1800ec7b3  pop     rdi
0x1800ec7b4  retn
```
