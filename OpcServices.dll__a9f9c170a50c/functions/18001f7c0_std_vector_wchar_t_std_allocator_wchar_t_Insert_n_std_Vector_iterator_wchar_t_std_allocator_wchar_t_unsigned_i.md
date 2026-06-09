# std::vector<wchar_t,std::allocator<wchar_t>>::_Insert_n(std::_Vector_iterator<wchar_t,std::allocator<wchar_t>>,unsigned __int64,wchar_t const &)

- ea: `0x18001f7c0`
- end: `0x18001fae1`
- name: `?_Insert_n@?$vector@_WV?$allocator@_W@std@@@std@@IEAAXV?$_Vector_iterator@_WV?$allocator@_W@std@@@2@_KAEB_W@Z`
- size: `801`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001ee8c`
- `0x18005d308`

## callees

- `0x18001f7c0`
- `0x180060268`
- `0x1800cce08`
- `0x1800cce54`
- `0x1800cd38c`
- `0x1800df33c`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001f9df`
- `msvcrt!memmove_s` at `0x18001fa04`
- `msvcrt!memmove_s` at `0x18001fa66`
- `msvcrt!memmove_s` at `0x18001fa85`
- `msvcrt!memmove_s` at `0x18001fabc`
- `msvcrt!memmove_s` at `0x18001f9df`
- `msvcrt!memmove_s` at `0x18001fa04`
- `msvcrt!memmove_s` at `0x18001fa66`
- `msvcrt!memmove_s` at `0x18001fa85`
- `msvcrt!memmove_s` at `0x18001fabc`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001fa3c`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001fa3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall std::vector<wchar_t>::_Insert_n(__int64 a1, _BYTE *a2, unsigned __int64 a3, __int16 *a4)
{
  char *result; // rax
  __int16 v8; // r10
  __int64 v9; // rcx
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // r8
  void **v12; // r13
  __int64 v13; // r9
  __int64 v14; // rax
  unsigned __int64 v15; // r12
  __int64 v16; // rax
  __int64 v17; // rax
  char *v18; // rax
  char *v19; // r15
  _BYTE *v20; // r8
  __int64 v21; // rcx
  char *v22; // rdi
  unsigned __int64 v23; // rcx
  __int16 v24; // ax
  __int64 v25; // rdx
  _BYTE *v26; // rcx
  _WORD *v27; // rdi
  unsigned __int64 v28; // rsi
  char *v29; // rdx
  rsize_t v30; // rdx
  char *v31; // rsi
  __int64 v32; // rdi
  char *v33; // r14
  __int64 v34; // r15
  unsigned __int64 v35; // rdx
  unsigned __int64 i; // rcx
  _QWORD pExceptionObject[10]; // [rsp+28h] [rbp-50h] BYREF
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h] BYREF
  const char *v39; // [rsp+80h] [rbp+8h] BYREF
  char *v40; // [rsp+90h] [rbp+18h] BYREF
  void *v41; // [rsp+98h] [rbp+20h]

  result = (char *)&retaddr;
  v8 = *a4;
  LOWORD(v39) = v8;
  LOWORD(v40) = v8;
  v9 = *(_QWORD *)(a1 + 8);
  if ( v9 )
  {
    v11 = (*(_QWORD *)(a1 + 24) - v9) >> 1;
    v10 = 0;
  }
  else
  {
    v10 = 0;
    v11 = 0;
  }
  if ( a3 )
  {
    v12 = (void **)(a1 + 16);
    if ( v9 )
      v13 = ((__int64)*v12 - v9) >> 1;
    else
      v13 = 0;
    if ( 0x7FFFFFFFFFFFFFFFLL - v13 < a3 )
      std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(v9);
    if ( v9 )
      v14 = ((__int64)*v12 - v9) >> 1;
    else
      v14 = 0;
    if ( v11 >= a3 + v14 )
    {
      v33 = (char *)*v12;
      v34 = 2 * a3;
      v35 = ((_BYTE *)*v12 - a2) >> 1;
      if ( v35 >= a3 )
      {
        v30 = 2 * (v34 >> 1);
        v31 = &v33[v30];
        if ( v34 >> 1 )
          memmove_s(*v12, v30, &v33[-v34], 2 * (v34 >> 1));
        *v12 = v31;
        v32 = (&v33[-v34] - a2) >> 1;
        if ( v32 > 0 )
          memmove_s(&v33[-2 * v32], 2 * v32, a2, 2 * v32);
        v29 = &a2[v34];
      }
      else
      {
        if ( v35 )
        {
          memmove_s(&a2[v34], 2 * v35, a2, 2 * v35);
          v8 = (__int16)v39;
        }
        v27 = *v12;
        v28 = a3 - (((_BYTE *)*v12 - a2) >> 1);
        if ( v28 )
        {
          for ( i = v28; i; --i )
            *v27++ = v8;
        }
        v29 = (char *)*v12;
        *v12 = (char *)*v12 + v34;
      }
      return (char *)std::fill<wchar_t *,wchar_t>(a2, v29, &v40);
    }
    else
    {
      v15 = 0;
      if ( 0x7FFFFFFFFFFFFFFFLL - (v11 >> 1) >= v11 )
        v15 = (v11 >> 1) + v11;
      if ( v9 )
        v16 = ((__int64)*v12 - v9) >> 1;
      else
        v16 = 0;
      if ( v15 < a3 + v16 )
      {
        if ( v9 )
          v17 = ((__int64)*v12 - v9) >> 1;
        else
          v17 = 0;
        v15 = v17 + a3;
      }
      if ( v15 )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / v15 < 2 )
        {
          v39 = 0;
          exception::exception((exception *)pExceptionObject, &v39);
          pExceptionObject[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)pExceptionObject;
        }
        v10 = v15;
      }
      v18 = (char *)operator new(2 * v10);
      v19 = v18;
      v41 = v18;
      v20 = *(_BYTE **)(a1 + 8);
      v21 = (a2 - v20) >> 1;
      v22 = &v18[2 * v21];
      v40 = v22;
      if ( v21 )
      {
        try
        {
          memmove_s(v18, 2 * v21, v20, 2 * v21);
        }
        catch ( ... )
        {
          operator delete(v41);
          throw;
        }
      }
      v23 = (2 * a3) >> 1;
      v24 = (__int16)v39;
      while ( v23 )
      {
        *(_WORD *)v22 = v24;
        v22 += 2;
        --v23;
      }
      v25 = ((_BYTE *)*v12 - a2) >> 1;
      if ( v25 )
        memmove_s(&v40[2 * a3], 2 * v25, a2, 2 * v25);
      v26 = *(_BYTE **)(a1 + 8);
      if ( v26 )
      {
        a3 += ((_BYTE *)*v12 - v26) >> 1;
        operator delete(v26);
      }
      *(_QWORD *)(a1 + 24) = &v19[2 * v15];
      result = &v19[2 * a3];
      *v12 = result;
      *(_QWORD *)(a1 + 8) = v19;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001f7c0  mov     rax, rsp
0x18001f7c3  push    rbx
0x18001f7c4  push    rsi
0x18001f7c5  push    rdi
0x18001f7c6  push    r12
0x18001f7c8  push    r13
0x18001f7ca  push    r14
0x18001f7cc  push    r15
0x18001f7ce  sub     rsp, 40h
0x18001f7d2  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x18001f7da  mov     rsi, r8
0x18001f7dd  mov     rbx, rdx
0x18001f7e0  mov     r14, rcx
0x18001f7e3  movzx   r10d, word ptr [r9]
0x18001f7e7  mov     [rax+8], r10w
0x18001f7ec  mov     [rax+18h], r10w
0x18001f7f1  mov     rcx, [rcx+8]
0x18001f7f5  test    rcx, rcx
0x18001f7f8  jnz     loc_18001FA10
0x18001f7fe  xor     edi, edi
0x18001f800  mov     r8d, edi
0x18001f803  test    rsi, rsi
0x18001f806  jz      loc_18001F91D
0x18001f80c  lea     r13, [r14+10h]
0x18001f810  test    rcx, rcx
0x18001f813  jnz     loc_18001F92D
0x18001f819  mov     r9, rdi
0x18001f81c  mov     rdx, 7FFFFFFFFFFFFFFFh
0x18001f826  mov     rax, rdx
0x18001f829  sub     rax, r9
0x18001f82c  cmp     rax, rsi
0x18001f82f  jb      loc_18001FA21
0x18001f835  test    rcx, rcx
0x18001f838  jnz     loc_18001F93C
0x18001f83e  mov     rax, rdi
0x18001f841  add     rax, rsi
0x18001f844  cmp     r8, rax
0x18001f847  jnb     loc_18001FA90
0x18001f84d  mov     rax, r8
0x18001f850  shr     rax, 1
0x18001f853  sub     rdx, rax
0x18001f856  cmp     rdx, r8
0x18001f859  mov     r12, rdi
0x18001f85c  jb      short loc_18001F862
0x18001f85e  lea     r12, [rax+r8]
0x18001f862  test    rcx, rcx
0x18001f865  jnz     loc_18001F94B
0x18001f86b  mov     rax, rdi
0x18001f86e  add     rax, rsi
0x18001f871  cmp     r12, rax
0x18001f874  jnb     short loc_18001F886
0x18001f876  test    rcx, rcx
0x18001f879  jnz     loc_18001F96E
0x18001f87f  mov     rax, rdi
0x18001f882  lea     r12, [rax+rsi]
0x18001f886  test    r12, r12
0x18001f889  jz      short loc_18001F8A4
0x18001f88b  xor     edx, edx
0x18001f88d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001f894  div     r12
0x18001f897  cmp     rax, 2
0x18001f89b  jb      loc_18001FA27
0x18001f8a1  mov     rdi, r12
0x18001f8a4  lea     rcx, [rdi+rdi]; Size
0x18001f8a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f8ad  mov     r15, rax
0x18001f8b0  mov     [rsp+78h+arg_18], rax
0x18001f8b8  mov     r8, [r14+8]; Source
0x18001f8bc  mov     rcx, rbx
0x18001f8bf  sub     rcx, r8
0x18001f8c2  sar     rcx, 1
0x18001f8c5  lea     rdx, [rcx+rcx]; DestinationSize
0x18001f8c9  lea     rdi, [rdx+rax]
0x18001f8cd  mov     [rsp+78h+arg_10], rdi
0x18001f8d5  jnz     loc_18001FA60
0x18001f8db  lea     r8, [rsi+rsi]
0x18001f8df  mov     rcx, r8
0x18001f8e2  shr     rcx, 1
0x18001f8e5  movzx   eax, word ptr [rsp+78h+arg_0]
0x18001f8ed  rep stosw
0x18001f8f0  mov     rdx, [r13+0]
0x18001f8f4  sub     rdx, rbx
0x18001f8f7  sar     rdx, 1
0x18001f8fa  jnz     loc_18001FA71
0x18001f900  mov     rcx, [r14+8]; Block
0x18001f904  test    rcx, rcx
0x18001f907  jnz     short loc_18001F95A
0x18001f909  lea     rax, [r15+r12*2]
0x18001f90d  mov     [r14+18h], rax
0x18001f911  lea     rax, [r15+rsi*2]
0x18001f915  mov     [r13+0], rax
0x18001f919  mov     [r14+8], r15
0x18001f91d  add     rsp, 40h
0x18001f921  pop     r15
0x18001f923  pop     r14
0x18001f925  pop     r13
0x18001f927  pop     r12
0x18001f929  pop     rdi
0x18001f92a  pop     rsi
0x18001f92b  pop     rbx
0x18001f92c  retn
0x18001f92d  mov     r9, [r13+0]
0x18001f931  sub     r9, rcx
0x18001f934  sar     r9, 1
0x18001f937  jmp     loc_18001F81C
0x18001f93c  mov     rax, [r13+0]
0x18001f940  sub     rax, rcx
0x18001f943  sar     rax, 1
0x18001f946  jmp     loc_18001F841
0x18001f94b  mov     rax, [r13+0]
0x18001f94f  sub     rax, rcx
0x18001f952  sar     rax, 1
0x18001f955  jmp     loc_18001F86E
0x18001f95a  mov     rax, [r13+0]
0x18001f95e  sub     rax, rcx
0x18001f961  sar     rax, 1
0x18001f964  add     rsi, rax
0x18001f967  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f96c  jmp     short loc_18001F909
0x18001f96e  mov     rax, [r13+0]
0x18001f972  sub     rax, rcx
0x18001f975  sar     rax, 1
0x18001f978  jmp     loc_18001F882
0x18001f97d  test    rdx, rdx
0x18001f980  jnz     loc_18001FAAF
0x18001f986  mov     rdi, [r13+0]
0x18001f98a  mov     rax, rdi
0x18001f98d  sub     rax, rbx
0x18001f990  sar     rax, 1
0x18001f993  sub     rsi, rax
0x18001f996  jnz     loc_18001FAD0
0x18001f99c  mov     rdx, [r13+0]
0x18001f9a0  lea     rax, [r15+rdx]
0x18001f9a4  mov     [r13+0], rax
0x18001f9a8  lea     r8, [rsp+78h+arg_10]
0x18001f9b0  mov     rcx, rbx
0x18001f9b3  call    ??$fill@PEA_W_W@std@@YAXPEA_W0AEB_W@Z; std::fill<wchar_t *,wchar_t>(wchar_t *,wchar_t *,wchar_t const &)
0x18001f9b8  jmp     loc_18001F91D
0x18001f9bd  mov     rax, r15
0x18001f9c0  sar     rax, 1
0x18001f9c3  lea     rdx, [rax+rax]; DestinationSize
0x18001f9c7  lea     rsi, [rdx+r14]
0x18001f9cb  mov     rdi, r14
0x18001f9ce  sub     rdi, r15
0x18001f9d1  test    rax, rax
0x18001f9d4  jz      short loc_18001F9E5
0x18001f9d6  mov     r9, rdx; SourceSize
0x18001f9d9  mov     r8, rdi; Source
0x18001f9dc  mov     rcx, r14; Destination
0x18001f9df  call    cs:__imp_memmove_s
0x18001f9e5  mov     [r13+0], rsi
0x18001f9e9  sub     rdi, rbx
0x18001f9ec  sar     rdi, 1
0x18001f9ef  test    rdi, rdi
0x18001f9f2  jle     short loc_18001FA0A
0x18001f9f4  lea     rdx, [rdi+rdi]; DestinationSize
0x18001f9f8  sub     r14, rdx
0x18001f9fb  mov     r9, rdx; SourceSize
0x18001f9fe  mov     r8, rbx; Source
0x18001fa01  mov     rcx, r14; Destination
0x18001fa04  call    cs:__imp_memmove_s
0x18001fa0a  lea     rdx, [r15+rbx]
0x18001fa0e  jmp     short loc_18001F9A8
0x18001fa10  mov     r8, [r14+18h]
0x18001fa14  sub     r8, rcx
0x18001fa17  sar     r8, 1
0x18001fa1a  xor     edi, edi
0x18001fa1c  jmp     loc_18001F803
0x18001fa21  call    ?_Xlen@?$vector@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@V?$allocator@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@@3@@std@@KAXXZ; std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(void)
0x18001fa27  mov     [rsp+78h+arg_0], rdi
0x18001fa2f  lea     rdx, [rsp+78h+arg_0]
0x18001fa37  lea     rcx, [rsp+78h+pExceptionObject]
0x18001fa3c  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18001fa42  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001fa49  mov     [rsp+78h+pExceptionObject], rax
0x18001fa4e  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001fa55  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001fa5a  call    _CxxThrowException_0
0x18001fa60  mov     r9, rdx; SourceSize
0x18001fa63  mov     rcx, r15; Destination
0x18001fa66  call    cs:__imp_memmove_s
0x18001fa6c  jmp     loc_18001F8DB
0x18001fa71  add     rdx, rdx; DestinationSize
0x18001fa74  mov     rcx, [rsp+78h+arg_10]
0x18001fa7c  add     rcx, r8; Destination
0x18001fa7f  mov     r9, rdx; SourceSize
0x18001fa82  mov     r8, rbx; Source
0x18001fa85  call    cs:__imp_memmove_s
0x18001fa8b  jmp     loc_18001F900
0x18001fa90  mov     r14, [r13+0]
0x18001fa94  lea     r15, [rsi+rsi]
0x18001fa98  mov     rdx, r14
0x18001fa9b  sub     rdx, rbx
0x18001fa9e  sar     rdx, 1
0x18001faa1  cmp     rdx, rsi
0x18001faa4  jnb     loc_18001F9BD
0x18001faaa  jmp     loc_18001F97D
0x18001faaf  add     rdx, rdx; DestinationSize
0x18001fab2  lea     rcx, [r15+rbx]; Destination
0x18001fab6  mov     r9, rdx; SourceSize
0x18001fab9  mov     r8, rbx; Source
0x18001fabc  call    cs:__imp_memmove_s
0x18001fac2  movzx   r10d, word ptr [rsp+78h+arg_0]
0x18001facb  jmp     loc_18001F986
0x18001fad0  movzx   eax, r10w
0x18001fad4  mov     rcx, rsi
0x18001fad7  rep stosw
0x18001fada  jmp     loc_18001F99C
```
