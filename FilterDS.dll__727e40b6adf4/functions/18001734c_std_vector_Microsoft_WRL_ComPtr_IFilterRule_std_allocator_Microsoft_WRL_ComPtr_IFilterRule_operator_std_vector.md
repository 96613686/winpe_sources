# std::vector<Microsoft::WRL::ComPtr<IFilterRule>,std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>>::operator=(std::vector<Microsoft::WRL::ComPtr<IFilterRule>,std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>> const &)

- ea: `0x18001734c`
- end: `0x180017587`
- name: `??4?$vector@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@std@@QEAAAEAV01@AEBV01@@Z`
- size: `571`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180017674`

## callees

- `0x180001a30`
- `0x180001bd8`
- `0x18000cd9c`
- `0x18001707c`
- `0x18001734c`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800174ff`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800174ff`

## pseudocode

```c
__int64 __fastcall std::vector<Microsoft::WRL::ComPtr<IFilterRule>>::operator=(__int64 a1, __int64 a2)
{
  _QWORD *v4; // r12
  _QWORD *v5; // rsi
  __int64 *v6; // rbx
  __int64 *v7; // r15
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  __int64 v10; // r15
  __int64 v11; // rcx
  __int64 *v12; // rsi
  __int64 v13; // rcx
  __int64 *v14; // rax
  __int64 v15; // rcx
  _QWORD *v17; // r12
  __int64 v18; // r15
  __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int64 v21; // rax
  __int64 v22; // rbx
  _QWORD *v23; // rax

  if ( a1 == a2 )
    return a1;
  v4 = *(_QWORD **)(a2 + 8);
  v5 = *(_QWORD **)a2;
  v6 = *(__int64 **)a1;
  v7 = *(__int64 **)(a1 + 8);
  if ( *(_QWORD **)a2 == v4 )
  {
    while ( v6 != v7 )
    {
      v13 = *v6;
      if ( *v6 )
      {
        *v6 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      ++v6;
    }
    v14 = *(__int64 **)a1;
    goto LABEL_32;
  }
  v8 = v4 - v5;
  v9 = v7 - v6;
  if ( v8 <= v9 )
  {
    do
    {
      v10 = *v5;
      if ( *v6 != *v5 )
      {
        if ( v10 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v10 + 8LL))(*v5);
        v11 = *v6;
        *v6 = v10;
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      ++v6;
      ++v5;
    }
    while ( v5 != v4 );
    v12 = *(__int64 **)(a1 + 8);
    while ( v6 != v12 )
    {
      v15 = *v6;
      if ( *v6 )
      {
        *v6 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      ++v6;
    }
    *(_QWORD *)(a1 + 8) = *(_QWORD *)a1 + 8 * ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 3);
    return a1;
  }
  if ( v8 <= (__int64)(*(_QWORD *)(a1 + 16) - (_QWORD)v6) >> 3 )
  {
    v17 = &v5[v9];
    while ( v5 != v17 )
    {
      v18 = *v5;
      if ( *v6 != *v5 )
      {
        if ( v18 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v18 + 8LL))(*v5);
        v19 = *v6;
        *v6 = v18;
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      ++v6;
      ++v5;
    }
    v14 = std::_Uninit_copy<Microsoft::WRL::ComPtr<IFilterRule> *,Microsoft::WRL::ComPtr<IFilterRule> *,std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>>(
            v17,
            *(_QWORD **)(a2 + 8),
            *(_QWORD **)(a1 + 8));
LABEL_32:
    *(_QWORD *)(a1 + 8) = v14;
    return a1;
  }
  if ( v6 )
  {
    while ( v6 != v7 )
    {
      v20 = *v6;
      if ( *v6 )
      {
        *v6 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      ++v6;
    }
    operator delete(*(void **)a1);
  }
  v21 = (__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 3;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  if ( v21 )
  {
    if ( v21 > 0x1FFFFFFFFFFFFFFFLL )
      std::vector<std::unique_ptr<FilterAgent>>::_Xlen();
    v22 = v21;
    v23 = operator new(8 * v21);
    if ( !v23 )
      std::_Xbad_alloc();
    *(_QWORD *)a1 = v23;
    *(_QWORD *)(a1 + 8) = v23;
    *(_QWORD *)(a1 + 16) = &v23[v22];
    try
    {
      *(_QWORD *)(a1 + 8) = std::_Uninit_copy<Microsoft::WRL::ComPtr<IFilterRule> *,Microsoft::WRL::ComPtr<IFilterRule> *,std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>>(
                              *(_QWORD **)a2,
                              *(_QWORD **)(a2 + 8),
                              v23);
    }
    catch ( ... )
    {
      std::vector<Microsoft::WRL::ComPtr<IFilterRule>>::_Tidy(a1);
      throw;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18001734c  mov     [rsp+arg_0], rcx
0x180017351  push    rbx
0x180017352  push    rsi
0x180017353  push    rdi
0x180017354  push    r12
0x180017356  push    r14
0x180017358  push    r15
0x18001735a  sub     rsp, 38h
0x18001735e  mov     r14, rdx
0x180017361  mov     rdi, rcx
0x180017364  cmp     rcx, rdx
0x180017367  jz      loc_180017451
0x18001736d  mov     r12, [rdx+8]
0x180017371  mov     rsi, [rdx]
0x180017374  mov     rbx, [rcx]
0x180017377  mov     r15, [rcx+8]
0x18001737b  cmp     rsi, r12
0x18001737e  jz      loc_180017409
0x180017384  mov     rdx, r12
0x180017387  sub     rdx, rsi
0x18001738a  sar     rdx, 3
0x18001738e  mov     rcx, r15
0x180017391  sub     rcx, rbx
0x180017394  sar     rcx, 3
0x180017398  cmp     rdx, rcx
0x18001739b  ja      loc_180017462
0x1800173a1  mov     r15, [rsi]
0x1800173a4  cmp     [rbx], r15
0x1800173a7  jz      short loc_1800173D6
0x1800173a9  test    r15, r15
0x1800173ac  jz      short loc_1800173BE
0x1800173ae  mov     rax, [r15]
0x1800173b1  mov     rcx, r15
0x1800173b4  mov     rax, [rax+8]
0x1800173b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173bd  nop
0x1800173be  mov     rcx, [rbx]
0x1800173c1  mov     [rbx], r15
0x1800173c4  test    rcx, rcx
0x1800173c7  jz      short loc_1800173D6
0x1800173c9  mov     rax, [rcx]
0x1800173cc  mov     rax, [rax+10h]
0x1800173d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173d5  nop
0x1800173d6  add     rbx, 8
0x1800173da  add     rsi, 8
0x1800173de  cmp     rsi, r12
0x1800173e1  jnz     short loc_1800173A1
0x1800173e3  mov     rsi, [rdi+8]
0x1800173e7  jmp     short loc_180017436
0x1800173e9  mov     rcx, [rbx]
0x1800173ec  test    rcx, rcx
0x1800173ef  jz      short loc_180017405
0x1800173f1  mov     qword ptr [rbx], 0
0x1800173f8  mov     rax, [rcx]
0x1800173fb  mov     rax, [rax+10h]
0x1800173ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017404  nop
0x180017405  add     rbx, 8
0x180017409  cmp     rbx, r15
0x18001740c  jnz     short loc_1800173E9
0x18001740e  mov     rax, [rdi]
0x180017411  jmp     loc_1800174CA
0x180017416  mov     rcx, [rbx]
0x180017419  test    rcx, rcx
0x18001741c  jz      short loc_180017432
0x18001741e  mov     qword ptr [rbx], 0
0x180017425  mov     rax, [rcx]
0x180017428  mov     rax, [rax+10h]
0x18001742c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017431  nop
0x180017432  add     rbx, 8
0x180017436  cmp     rbx, rsi
0x180017439  jnz     short loc_180017416
0x18001743b  mov     rcx, [r14+8]
0x18001743f  sub     rcx, [r14]
0x180017442  sar     rcx, 3
0x180017446  mov     rax, [rdi]
0x180017449  lea     rcx, [rax+rcx*8]
0x18001744d  mov     [rdi+8], rcx
0x180017451  mov     rax, rdi
0x180017454  add     rsp, 38h
0x180017458  pop     r15
0x18001745a  pop     r14
0x18001745c  pop     r12
0x18001745e  pop     rdi
0x18001745f  pop     rsi
0x180017460  pop     rbx
0x180017461  retn
0x180017462  mov     rax, [rdi+10h]
0x180017466  sub     rax, rbx
0x180017469  sar     rax, 3
0x18001746d  cmp     rdx, rax
0x180017470  ja      short loc_1800174D0
0x180017472  lea     r12, [rsi+rcx*8]
0x180017476  jmp     short loc_1800174B5
0x180017478  mov     r15, [rsi]
0x18001747b  cmp     [rbx], r15
0x18001747e  jz      short loc_1800174AD
0x180017480  test    r15, r15
0x180017483  jz      short loc_180017495
0x180017485  mov     rax, [r15]
0x180017488  mov     rcx, r15
0x18001748b  mov     rax, [rax+8]
0x18001748f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017494  nop
0x180017495  mov     rcx, [rbx]
0x180017498  mov     [rbx], r15
0x18001749b  test    rcx, rcx
0x18001749e  jz      short loc_1800174AD
0x1800174a0  mov     rax, [rcx]
0x1800174a3  mov     rax, [rax+10h]
0x1800174a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174ac  nop
0x1800174ad  add     rbx, 8
0x1800174b1  add     rsi, 8
0x1800174b5  cmp     rsi, r12
0x1800174b8  jnz     short loc_180017478
0x1800174ba  mov     r8, [rdi+8]
0x1800174be  mov     rdx, [r14+8]
0x1800174c2  mov     rcx, r12
0x1800174c5  call    ??$_Uninit_copy@PEAV?$ComPtr@UIFilterRule@@@WRL@Microsoft@@PEAV123@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@std@@YAPEAV?$ComPtr@UIFilterRule@@@WRL@Microsoft@@PEAV123@00AEAU?$_Wrap_alloc@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<Microsoft::WRL::ComPtr<IFilterRule> *,Microsoft::WRL::ComPtr<IFilterRule> *,std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>>(Microsoft::WRL::ComPtr<IFilterRule> *,Microsoft::WRL::ComPtr<IFilterRule> *,Microsoft::WRL::ComPtr<IFilterRule> *,std::_Wrap_alloc<std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>> &,std::_Nonscalar_ptr_iterator_tag)
0x1800174ca  mov     [rdi+8], rax
0x1800174ce  jmp     short loc_180017451
0x1800174d0  test    rbx, rbx
0x1800174d3  jz      short loc_180017505
0x1800174d5  jmp     short loc_1800174F7
0x1800174d7  mov     rcx, [rbx]
0x1800174da  test    rcx, rcx
0x1800174dd  jz      short loc_1800174F3
0x1800174df  mov     qword ptr [rbx], 0
0x1800174e6  mov     rax, [rcx]
0x1800174e9  mov     rax, [rax+10h]
0x1800174ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174f2  nop
0x1800174f3  add     rbx, 8
0x1800174f7  cmp     rbx, r15
0x1800174fa  jnz     short loc_1800174D7
0x1800174fc  mov     rcx, [rdi]
0x1800174ff  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180017505  mov     rax, [r14+8]
0x180017509  sub     rax, [r14]
0x18001750c  sar     rax, 3
0x180017510  mov     qword ptr [rdi], 0
0x180017517  mov     qword ptr [rdi+8], 0
0x18001751f  mov     qword ptr [rdi+10h], 0
0x180017527  test    rax, rax
0x18001752a  jz      loc_180017451
0x180017530  mov     rcx, 1FFFFFFFFFFFFFFFh
0x18001753a  cmp     rax, rcx
0x18001753d  ja      short loc_180017581
0x18001753f  lea     rbx, ds:0[rax*8]
0x180017547  mov     rcx, rbx; Size
0x18001754a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001754f  test    rax, rax
0x180017552  jz      short loc_18001757B
0x180017554  mov     [rdi], rax
0x180017557  mov     [rdi+8], rax
0x18001755b  lea     rcx, [rbx+rax]
0x18001755f  mov     [rdi+10h], rcx
0x180017563  mov     r8, rax
0x180017566  mov     rdx, [r14+8]
0x18001756a  mov     rcx, [r14]
0x18001756d  call    ??$_Uninit_copy@PEAV?$ComPtr@UIFilterRule@@@WRL@Microsoft@@PEAV123@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@std@@YAPEAV?$ComPtr@UIFilterRule@@@WRL@Microsoft@@PEAV123@00AEAU?$_Wrap_alloc@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<Microsoft::WRL::ComPtr<IFilterRule> *,Microsoft::WRL::ComPtr<IFilterRule> *,std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>>(Microsoft::WRL::ComPtr<IFilterRule> *,Microsoft::WRL::ComPtr<IFilterRule> *,Microsoft::WRL::ComPtr<IFilterRule> *,std::_Wrap_alloc<std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>> &,std::_Nonscalar_ptr_iterator_tag)
0x180017572  mov     [rdi+8], rax
0x180017576  jmp     loc_180017451
0x18001757b  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180017581  call    ?_Xlen@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::unique_ptr<FilterAgent>>::_Xlen(void)
```
