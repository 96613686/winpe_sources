# std::vector<uchar,std::allocator<uchar>>::_Insert<uchar const *>(std::_Vector_iterator<uchar,std::allocator<uchar>>,uchar const *,uchar const *,std::forward_iterator_tag)

- ea: `0x180022f9c`
- end: `0x18002322f`
- name: `??$_Insert@PEBE@?$vector@EV?$allocator@E@std@@@std@@QEAAXV?$_Vector_iterator@EV?$allocator@E@std@@@1@PEBE1Uforward_iterator_tag@1@@Z`
- size: `659`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800094c0`
- `0x18000ac48`
- `0x180020cc8`
- `0x180024108`
- `0x18008465c`
- `0x1800850cc`
- `0x18008577c`
- `0x180087264`
- `0x18008ea2c`
- `0x1800b38b4`
- `0x1801175e4`

## callees

- `0x180022f9c`
- `0x180060268`
- `0x1800786c0`
- `0x1800b377c`
- `0x1800cce08`
- `0x1800cce54`
- `0x1800cd38c`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800230c3`
- `msvcrt!memmove_s` at `0x1800230da`
- `msvcrt!memmove_s` at `0x1800230f2`
- `msvcrt!memmove_s` at `0x180023176`
- `msvcrt!memmove_s` at `0x180023196`
- `msvcrt!memmove_s` at `0x1800231c2`
- `msvcrt!memmove_s` at `0x1800230c3`
- `msvcrt!memmove_s` at `0x1800230da`
- `msvcrt!memmove_s` at `0x1800230f2`
- `msvcrt!memmove_s` at `0x180023176`
- `msvcrt!memmove_s` at `0x180023196`
- `msvcrt!memmove_s` at `0x1800231c2`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18002320b`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18002320b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall std::vector<unsigned char>::_Insert<unsigned char const *>(
        __int64 a1,
        _BYTE *a2,
        char *a3,
        __int64 a4)
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
      std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen();
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
  }
  return result;
}

```

## disassembly

```asm
0x180022f9c  mov     rax, rsp
0x180022f9f  mov     [rax+18h], r8
0x180022fa3  push    rdi
0x180022fa4  push    r12
0x180022fa6  push    r13
0x180022fa8  push    r14
0x180022faa  push    r15
0x180022fac  sub     rsp, 40h
0x180022fb0  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180022fb8  mov     [rax+10h], rbx
0x180022fbc  mov     [rax+20h], rsi
0x180022fc0  mov     r14, r9
0x180022fc3  mov     r12, r8
0x180022fc6  mov     rbx, rdx
0x180022fc9  mov     r13, rcx
0x180022fcc  mov     rdi, r9
0x180022fcf  sub     rdi, r8
0x180022fd2  mov     rdx, [rcx+8]
0x180022fd6  test    rdx, rdx
0x180022fd9  jz      loc_180023128
0x180022fdf  mov     r10, [rcx+18h]
0x180022fe3  sub     r10, rdx
0x180022fe6  test    rdi, rdi
0x180022fe9  jnz     short loc_180023005
0x180022feb  lea     r11, [rsp+68h+var_28]
0x180022ff0  mov     rbx, [r11+38h]
0x180022ff4  mov     rsi, [r11+48h]
0x180022ff8  mov     rsp, r11
0x180022ffb  pop     r15
0x180022ffd  pop     r14
0x180022fff  pop     r13
0x180023001  pop     r12
0x180023003  pop     rdi
0x180023004  retn
0x180023005  lea     rsi, [rcx+10h]
0x180023009  test    rdx, rdx
0x18002300c  jz      loc_180023139
0x180023012  mov     rax, [rsi]
0x180023015  sub     rax, rdx
0x180023018  not     rax
0x18002301b  cmp     rax, rdi
0x18002301e  jb      loc_1800231E5
0x180023024  test    rdx, rdx
0x180023027  jz      loc_180023140
0x18002302d  mov     rax, [rsi]
0x180023030  sub     rax, rdx
0x180023033  add     rax, rdi
0x180023036  cmp     r10, rax
0x180023039  jnb     loc_180023159
0x18002303f  mov     rcx, r10
0x180023042  shr     rcx, 1
0x180023045  mov     rax, rcx
0x180023048  not     rax
0x18002304b  cmp     rax, r10
0x18002304e  jnb     loc_180023130
0x180023054  xor     r14d, r14d
0x180023057  test    rdx, rdx
0x18002305a  jz      loc_180023147
0x180023060  mov     rax, [rsi]
0x180023063  sub     rax, rdx
0x180023066  add     rax, rdi
0x180023069  cmp     r14, rax
0x18002306c  jnb     short loc_180023081
0x18002306e  test    rdx, rdx
0x180023071  jz      loc_180023152
0x180023077  mov     rax, [rsi]
0x18002307a  sub     rax, rdx
0x18002307d  lea     r14, [rdi+rax]
0x180023081  test    r14, r14
0x180023084  jz      loc_1800231EB
0x18002308a  xor     edx, edx
0x18002308c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023090  div     r14
0x180023093  cmp     rax, 1
0x180023097  jb      loc_1800231F2
0x18002309d  mov     rcx, r14; Size
0x1800230a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800230a5  mov     r15, rax
0x1800230a8  mov     [rsp+68h+arg_0], rax
0x1800230ad  mov     r8, [r13+8]; Source
0x1800230b1  mov     rdx, rbx
0x1800230b4  sub     rdx, r8; DestinationSize
0x1800230b7  lea     r12, [rdx+rax]
0x1800230bb  jz      short loc_1800230C9
0x1800230bd  mov     r9, rdx; SourceSize
0x1800230c0  mov     rcx, rax; Destination
0x1800230c3  call    cs:__imp_memmove_s
0x1800230c9  mov     r9, rdi; SourceSize
0x1800230cc  mov     r8, [rsp+68h+Source]; Source
0x1800230d4  mov     rdx, rdi; DestinationSize
0x1800230d7  mov     rcx, r12; Destination
0x1800230da  call    cs:__imp_memmove_s
0x1800230e0  mov     rdx, [rsi]
0x1800230e3  sub     rdx, rbx; DestinationSize
0x1800230e6  jz      short loc_1800230F9
0x1800230e8  lea     rcx, [r12+rdi]; Destination
0x1800230ec  mov     r9, rdx; SourceSize
0x1800230ef  mov     r8, rbx; Source
0x1800230f2  call    cs:__imp_memmove_s
0x1800230f8  nop
0x1800230f9  mov     rcx, [r13+8]; Block
0x1800230fd  test    rcx, rcx
0x180023100  jz      short loc_18002314E
0x180023102  mov     rbx, [rsi]
0x180023105  sub     rbx, rcx
0x180023108  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002310d  lea     rax, [r15+r14]
0x180023111  mov     [r13+18h], rax
0x180023115  lea     rax, [rdi+rbx]
0x180023119  add     rax, r15
0x18002311c  mov     [rsi], rax
0x18002311f  mov     [r13+8], r15
0x180023123  jmp     loc_180022FEB
0x180023128  xor     r10d, r10d
0x18002312b  jmp     loc_180022FE6
0x180023130  lea     r14, [rcx+r10]
0x180023134  jmp     loc_180023057
0x180023139  xor     eax, eax
0x18002313b  jmp     loc_180023018
0x180023140  xor     eax, eax
0x180023142  jmp     loc_180023033
0x180023147  xor     eax, eax
0x180023149  jmp     loc_180023066
0x18002314e  xor     ebx, ebx
0x180023150  jmp     short loc_18002310D
0x180023152  xor     eax, eax
0x180023154  jmp     loc_18002307D
0x180023159  mov     r15, [rsi]
0x18002315c  mov     rdx, r15
0x18002315f  sub     rdx, rbx; DestinationSize
0x180023162  cmp     rdx, rdi
0x180023165  jnb     short loc_1800231B3
0x180023167  test    rdx, rdx
0x18002316a  jz      short loc_18002317C
0x18002316c  lea     rcx, [rdi+rbx]; Destination
0x180023170  mov     r9, rdx; SourceSize
0x180023173  mov     r8, rbx; Source
0x180023176  call    cs:__imp_memmove_s
0x18002317c  mov     r15, [rsi]
0x18002317f  sub     r15, rbx
0x180023182  add     r15, r12
0x180023185  sub     r14, r15
0x180023188  jz      short loc_18002319D
0x18002318a  mov     r9, r14; SourceSize
0x18002318d  mov     r8, r15; Source
0x180023190  mov     rdx, r14; DestinationSize
0x180023193  mov     rcx, [rsi]; Destination
0x180023196  call    cs:__imp_memmove_s
0x18002319c  nop
0x18002319d  add     [rsi], rdi
0x1800231a0  mov     rdx, r15
0x1800231a3  mov     r8, rbx
0x1800231a6  mov     rcx, r12; Source
0x1800231a9  call    ??$copy@PEBEPEAE@std@@YAPEAEPEBE0PEAE@Z; std::copy<uchar const *,uchar *>(uchar const *,uchar const *,uchar *)
0x1800231ae  jmp     loc_180022FEB
0x1800231b3  mov     r8, r15
0x1800231b6  sub     r8, rdi; Source
0x1800231b9  mov     r9, rdi; SourceSize
0x1800231bc  mov     rdx, rdi; DestinationSize
0x1800231bf  mov     rcx, r15; Destination
0x1800231c2  call    cs:__imp_memmove_s
0x1800231c8  lea     rax, [rdi+r15]
0x1800231cc  mov     [rsi], rax
0x1800231cf  mov     rdx, r15
0x1800231d2  sub     rdx, rdi
0x1800231d5  mov     r8, r15
0x1800231d8  mov     rcx, rbx; Source
0x1800231db  call    ??$copy_backward@PEAEPEAE@std@@YAPEAEPEAE00@Z; std::copy_backward<uchar *,uchar *>(uchar *,uchar *,uchar *)
0x1800231e0  mov     rdx, r14
0x1800231e3  jmp     short loc_1800231A3
0x1800231e5  call    ?_Xlen@?$vector@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@V?$allocator@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@@3@@std@@KAXXZ; std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(void)
0x1800231eb  xor     ecx, ecx
0x1800231ed  jmp     loc_1800230A0
0x1800231f2  mov     [rsp+68h+Source], 0
0x1800231fe  lea     rdx, [rsp+68h+Source]
0x180023206  lea     rcx, [rsp+68h+pExceptionObject]
0x18002320b  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180023211  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180023218  mov     [rsp+68h+pExceptionObject], rax
0x18002321d  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180023224  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180023229  call    _CxxThrowException_0
```
