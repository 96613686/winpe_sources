# std::vector<uchar,std::allocator<uchar>>::_Insert<std::_Vector_iterator<uchar,std::allocator<uchar>>>(std::_Vector_iterator<uchar,std::allocator<uchar>>,std::_Vector_iterator<uchar,std::allocator<uchar>>,std::_Vector_iterator<uchar,std::allocator<uchar>>,std::forward_iterator_tag)

- ea: `0x180061088`
- end: `0x18006132e`
- name: `??$_Insert@V?$_Vector_iterator@EV?$allocator@E@std@@@std@@@?$vector@EV?$allocator@E@std@@@std@@QEAAXV?$_Vector_iterator@EV?$allocator@E@std@@@1@00Uforward_iterator_tag@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18006104c`

## callees

- `0x180060268`
- `0x180061088`
- `0x180061334`
- `0x1800b377c`
- `0x1800cce08`
- `0x1800cce54`
- `0x1800cd38c`

## import_xrefs

- `msvcrt!memmove_s` at `0x18006119e`
- `msvcrt!memmove_s` at `0x1800611cc`
- `msvcrt!memmove_s` at `0x180061259`
- `msvcrt!memmove_s` at `0x18006130e`
- `msvcrt!memmove_s` at `0x18006119e`
- `msvcrt!memmove_s` at `0x1800611cc`
- `msvcrt!memmove_s` at `0x180061259`
- `msvcrt!memmove_s` at `0x18006130e`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1800612c6`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1800612c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::vector<unsigned char>::_Insert<std::_Vector_iterator<unsigned char>>(
        __int64 a1,
        _BYTE *a2,
        _BYTE *a3,
        _BYTE *a4)
{
  _BYTE *v5; // rbx
  rsize_t v7; // r12
  __int64 v8; // rdx
  unsigned __int64 v9; // r8
  void **v10; // r15
  unsigned __int64 v11; // rax
  char *v12; // rax
  size_t v13; // rdi
  char *v14; // rax
  size_t v15; // rcx
  char *v16; // r13
  _BYTE *v17; // r8
  __int64 v18; // rax
  void *v19; // rax
  const char *v20; // rsi
  _BYTE *v21; // rcx
  signed __int64 v22; // rbx
  char *v23; // rax
  _BYTE *v24; // rdi
  char *v25; // r13
  rsize_t v26; // rdx
  _QWORD pExceptionObject[10]; // [rsp+38h] [rbp-50h] BYREF
  const char *v28; // [rsp+90h] [rbp+8h] BYREF
  __int64 v29; // [rsp+A0h] [rbp+18h]
  void *v30; // [rsp+A8h] [rbp+20h]

  v28 = (const char *)a1;
  v5 = a3;
  v7 = a4 - a3;
  v8 = *(_QWORD *)(a1 + 8);
  if ( v8 )
    v9 = *(_QWORD *)(a1 + 24) - v8;
  else
    v9 = 0;
  if ( v7 )
  {
    v10 = (void **)(a1 + 16);
    if ( v8 )
      v11 = (unsigned __int64)*v10 - v8;
    else
      v11 = 0;
    if ( ~v11 < v7 )
      std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(a1);
    if ( v8 )
      v12 = (char *)*v10 - v8;
    else
      v12 = 0;
    if ( v9 >= (unsigned __int64)&v12[v7] )
    {
      v25 = (char *)*v10;
      v26 = (_BYTE *)*v10 - a2;
      if ( v26 < v7 )
      {
        if ( v26 )
          memmove_s(&a2[v7], v26, a2, (_BYTE *)*v10 - a2);
        try
        {
          v24 = &v5[(_BYTE *)*v10 - a2];
          std::_Uninit_copy<std::_Vector_iterator<unsigned char>,unsigned char *,std::allocator<unsigned char>>(
            v24,
            a4,
            *v10);
          *v10 = (char *)*v10 + v7;
          while ( v5 != v24 )
            *a2++ = *v5++;
        }
        catch ( ... )
        {
          throw;
        }
      }
      else
      {
        memmove_s(*v10, v7, &v25[-v7], v7);
        *v10 = &v25[v7];
        std::copy_backward<unsigned char *,unsigned char *>(a2);
        while ( v5 != a4 )
          *a2++ = *v5++;
      }
    }
    else
    {
      if ( ~(v9 >> 1) >= v9 )
        v13 = (v9 >> 1) + v9;
      else
        v13 = 0;
      if ( v8 )
        v14 = (char *)*v10 - v8;
      else
        v14 = 0;
      if ( v13 < (unsigned __int64)&v14[v7] )
      {
        if ( v8 )
          v23 = (char *)*v10 - v8;
        else
          v23 = 0;
        v13 = (size_t)&v23[v7];
      }
      if ( v13 )
      {
        if ( !(0xFFFFFFFFFFFFFFFFuLL / v13) )
        {
          v28 = 0;
          exception::exception((exception *)pExceptionObject, &v28);
          pExceptionObject[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)pExceptionObject;
        }
        v15 = v13;
      }
      else
      {
        v15 = 0;
      }
      v16 = (char *)operator new(v15);
      v30 = v16;
      v17 = (_BYTE *)*((_QWORD *)v28 + 1);
      v18 = a2 - v17;
      v29 = a2 - v17;
      if ( a2 != v17 )
      {
        memmove_s(v16, a2 - v17, v17, a2 - v17);
        v18 = v29;
      }
      try
      {
        v19 = (void *)std::_Uninit_copy<std::_Vector_iterator<unsigned char>,unsigned char *,std::allocator<unsigned char>>(
                        v5,
                        a4,
                        &v16[v18]);
        if ( *v10 != a2 )
          memmove_s(v19, (_BYTE *)*v10 - a2, a2, (_BYTE *)*v10 - a2);
      }
      catch ( ... )
      {
        operator delete(v30);
        throw;
      }
      v20 = v28;
      v21 = (_BYTE *)*((_QWORD *)v28 + 1);
      if ( v21 )
      {
        v22 = (_BYTE *)*v10 - v21;
        operator delete(v21);
      }
      else
      {
        v22 = 0;
      }
      *((_QWORD *)v20 + 3) = &v16[v13];
      *v10 = &v16[v7 + v22];
      *((_QWORD *)v20 + 1) = v16;
    }
  }
}

```

## disassembly

```asm
0x180061088  mov     [rsp+arg_0], rcx
0x18006108d  push    rbx
0x18006108e  push    rsi
0x18006108f  push    rdi
0x180061090  push    r12
0x180061092  push    r13
0x180061094  push    r14
0x180061096  push    r15
0x180061098  sub     rsp, 50h
0x18006109c  mov     [rsp+88h+var_58], 0FFFFFFFFFFFFFFFEh
0x1800610a5  mov     rsi, r9
0x1800610a8  mov     rbx, r8
0x1800610ab  mov     r14, rdx
0x1800610ae  mov     r12, r9
0x1800610b1  sub     r12, r8
0x1800610b4  mov     rdx, [rcx+8]
0x1800610b8  test    rdx, rdx
0x1800610bb  jz      short loc_1800610D9
0x1800610bd  mov     r8, [rcx+18h]
0x1800610c1  sub     r8, rdx
0x1800610c4  test    r12, r12
0x1800610c7  jnz     short loc_1800610DE
0x1800610c9  add     rsp, 50h
0x1800610cd  pop     r15
0x1800610cf  pop     r14
0x1800610d1  pop     r13
0x1800610d3  pop     r12
0x1800610d5  pop     rdi
0x1800610d6  pop     rsi
0x1800610d7  pop     rbx
0x1800610d8  retn
0x1800610d9  xor     r8d, r8d
0x1800610dc  jmp     short loc_1800610C4
0x1800610de  lea     r15, [rcx+10h]
0x1800610e2  test    rdx, rdx
0x1800610e5  jz      loc_180061213
0x1800610eb  mov     rax, [r15]
0x1800610ee  sub     rax, rdx
0x1800610f1  not     rax
0x1800610f4  cmp     rax, r12
0x1800610f7  jb      loc_18006122C
0x1800610fd  test    rdx, rdx
0x180061100  jz      loc_18006121A
0x180061106  mov     rax, [r15]
0x180061109  sub     rax, rdx
0x18006110c  add     rax, r12
0x18006110f  cmp     r8, rax
0x180061112  jnb     loc_1800612EA
0x180061118  mov     rcx, r8
0x18006111b  shr     rcx, 1
0x18006111e  mov     rax, rcx
0x180061121  not     rax
0x180061124  cmp     rax, r8
0x180061127  jnb     loc_18006120A
0x18006112d  xor     edi, edi
0x18006112f  test    rdx, rdx
0x180061132  jz      loc_180061221
0x180061138  mov     rax, [r15]
0x18006113b  sub     rax, rdx
0x18006113e  add     rax, r12
0x180061141  cmp     rdi, rax
0x180061144  jb      loc_180061232
0x18006114a  test    rdi, rdi
0x18006114d  jz      loc_1800612A6
0x180061153  xor     edx, edx
0x180061155  or      rax, 0FFFFFFFFFFFFFFFFh
0x180061159  div     rdi
0x18006115c  cmp     rax, 1
0x180061160  jb      loc_1800612AD
0x180061166  mov     rcx, rdi; Size
0x180061169  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006116e  mov     r13, rax
0x180061171  mov     [rsp+88h+arg_18], rax
0x180061179  mov     rax, [rsp+88h+arg_0]
0x180061181  mov     r8, [rax+8]; Source
0x180061185  mov     rax, r14
0x180061188  sub     rax, r8
0x18006118b  mov     [rsp+88h+arg_10], rax
0x180061193  jz      short loc_1800611AC
0x180061195  mov     r9, rax; SourceSize
0x180061198  mov     rdx, rax; DestinationSize
0x18006119b  mov     rcx, r13; Destination
0x18006119e  call    cs:__imp_memmove_s
0x1800611a4  mov     rax, [rsp+88h+arg_10]
0x1800611ac  lea     r8, [rax+r13]
0x1800611b0  mov     rdx, rsi
0x1800611b3  mov     rcx, rbx
0x1800611b6  call    ??$_Uninit_copy@V?$_Vector_iterator@EV?$allocator@E@std@@@std@@PEAEV?$allocator@E@2@@std@@YAPEAEV?$_Vector_iterator@EV?$allocator@E@std@@@0@0PEAEAEAV?$allocator@E@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_copy<std::_Vector_iterator<uchar>,uchar *,std::allocator<uchar>>(std::_Vector_iterator<uchar>,std::_Vector_iterator<uchar>,uchar *,std::allocator<uchar> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x1800611bb  mov     rdx, [r15]
0x1800611be  sub     rdx, r14; DestinationSize
0x1800611c1  jz      short loc_1800611D3
0x1800611c3  mov     r9, rdx; SourceSize
0x1800611c6  mov     r8, r14; Source
0x1800611c9  mov     rcx, rax; Destination
0x1800611cc  call    cs:__imp_memmove_s
0x1800611d2  nop
0x1800611d3  mov     rsi, [rsp+88h+arg_0]
0x1800611db  mov     rcx, [rsi+8]; Block
0x1800611df  test    rcx, rcx
0x1800611e2  jz      short loc_180061228
0x1800611e4  mov     rbx, [r15]
0x1800611e7  sub     rbx, rcx
0x1800611ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800611ef  lea     rax, [rdi+r13]
0x1800611f3  mov     [rsi+18h], rax
0x1800611f7  lea     rax, [r12+rbx]
0x1800611fb  add     rax, r13
0x1800611fe  mov     [r15], rax
0x180061201  mov     [rsi+8], r13
0x180061205  jmp     loc_1800610C9
0x18006120a  lea     rdi, [rcx+r8]
0x18006120e  jmp     loc_18006112F
0x180061213  xor     eax, eax
0x180061215  jmp     loc_1800610F1
0x18006121a  xor     eax, eax
0x18006121c  jmp     loc_18006110C
0x180061221  xor     eax, eax
0x180061223  jmp     loc_18006113E
0x180061228  xor     ebx, ebx
0x18006122a  jmp     short loc_1800611EF
0x18006122c  call    ?_Xlen@?$vector@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@V?$allocator@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@@3@@std@@KAXXZ; std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(void)
0x180061232  test    rdx, rdx
0x180061235  jnz     short loc_180061242
0x180061237  xor     eax, eax
0x180061239  lea     rdi, [r12+rax]
0x18006123d  jmp     loc_18006114A
0x180061242  mov     rax, [r15]
0x180061245  sub     rax, rdx
0x180061248  jmp     short loc_180061239
0x18006124a  test    rdx, rdx
0x18006124d  jz      short loc_18006125F
0x18006124f  lea     rcx, [r12+r14]; Destination
0x180061253  mov     r9, rdx; SourceSize
0x180061256  mov     r8, r14; Source
0x180061259  call    cs:__imp_memmove_s
0x18006125f  mov     rdi, [r15]
0x180061262  sub     rdi, r14
0x180061265  add     rdi, rbx
0x180061268  mov     r8, [r15]
0x18006126b  mov     rdx, rsi
0x18006126e  mov     rcx, rdi
0x180061271  call    ??$_Uninit_copy@V?$_Vector_iterator@EV?$allocator@E@std@@@std@@PEAEV?$allocator@E@2@@std@@YAPEAEV?$_Vector_iterator@EV?$allocator@E@std@@@0@0PEAEAEAV?$allocator@E@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_copy<std::_Vector_iterator<uchar>,uchar *,std::allocator<uchar>>(std::_Vector_iterator<uchar>,std::_Vector_iterator<uchar>,uchar *,std::allocator<uchar> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x180061276  nop
0x180061277  add     [r15], r12
0x18006127a  cmp     rbx, rdi
0x18006127d  jz      loc_1800610C9
0x180061283  mov     al, [rbx]
0x180061285  mov     [r14], al
0x180061288  inc     r14
0x18006128b  inc     rbx
0x18006128e  jmp     short loc_18006127A
0x180061290  cmp     rbx, rsi
0x180061293  jz      loc_1800610C9
0x180061299  mov     al, [rbx]
0x18006129b  mov     [r14], al
0x18006129e  inc     r14
0x1800612a1  inc     rbx
0x1800612a4  jmp     short loc_180061290
0x1800612a6  xor     ecx, ecx
0x1800612a8  jmp     loc_180061169
0x1800612ad  mov     [rsp+88h+arg_0], 0
0x1800612b9  lea     rdx, [rsp+88h+arg_0]
0x1800612c1  lea     rcx, [rsp+88h+pExceptionObject]
0x1800612c6  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x1800612cc  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800612d3  mov     [rsp+88h+pExceptionObject], rax
0x1800612d8  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800612df  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800612e4  call    _CxxThrowException_0
0x1800612ea  mov     r13, [r15]
0x1800612ed  mov     rdx, r13
0x1800612f0  sub     rdx, r14; DestinationSize
0x1800612f3  cmp     rdx, r12
0x1800612f6  jb      loc_18006124A
0x1800612fc  mov     rdi, r13
0x1800612ff  sub     rdi, r12
0x180061302  mov     r9, r12; SourceSize
0x180061305  mov     r8, rdi; Source
0x180061308  mov     rdx, r12; DestinationSize
0x18006130b  mov     rcx, r13; Destination
0x18006130e  call    cs:__imp_memmove_s
0x180061314  lea     rax, [r12+r13]
0x180061318  mov     [r15], rax
0x18006131b  mov     r8, r13
0x18006131e  mov     rdx, rdi
0x180061321  mov     rcx, r14; Source
0x180061324  call    ??$copy_backward@PEAEPEAE@std@@YAPEAEPEAE00@Z; std::copy_backward<uchar *,uchar *>(uchar *,uchar *,uchar *)
0x180061329  jmp     loc_180061290
```
