# std::vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>>::_Reallocate(unsigned __int64)

- ea: `0x18000cbb4`
- end: `0x18000cc96`
- name: `?_Reallocate@?$vector@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@IEAAX_K@Z`
- size: `226`
- prototype: `__int64 *__fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000cc9c`

## callees

- `0x180001a30`
- `0x180001bd8`
- `0x180008130`
- `0x18000cbb4`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000cc60`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cc60`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall std::vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>::_Reallocate(
        __int64 a1,
        unsigned __int64 a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // rcx
  __int64 *v6; // r14
  __int64 *v7; // r13
  __int64 v8; // r12
  __int64 **v9; // rsi
  __int64 *result; // rax
  _QWORD *v11; // [rsp+68h] [rbp+10h]

  v4 = 0;
  v11 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL || (v4 = operator new(8 * a2), (v11 = v4) == 0) )
      std::_Xbad_alloc();
  }
  try
  {
    v9 = (__int64 **)(a1 + 8);
    std::_Uninit_move<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy> *,wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>,wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>(
      *(__int64 **)a1,
      *(__int64 **)(a1 + 8),
      v4);
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<unsigned char>>::deallocate(v5, v11);
    throw;
  }
  v6 = *(__int64 **)a1;
  v7 = *v9;
  v8 = ((__int64)*v9 - *(_QWORD *)a1) >> 3;
  if ( *(_QWORD *)a1 )
  {
    if ( v6 != v7 )
    {
      do
      {
        if ( *v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)*v6 + 16LL))(*v6);
        ++v6;
      }
      while ( v6 != v7 );
      v9 = (__int64 **)(a1 + 8);
    }
    operator delete(*(void **)a1);
  }
  *(_QWORD *)(a1 + 16) = &v4[a2];
  result = &v4[v8];
  *v9 = result;
  *(_QWORD *)a1 = v4;
  return result;
}

```

## disassembly

```asm
0x18000cbb4  mov     [rsp+arg_0], rbx
0x18000cbb9  mov     [rsp+arg_10], rsi
0x18000cbbe  push    rdi
0x18000cbbf  push    r12
0x18000cbc1  push    r13
0x18000cbc3  push    r14
0x18000cbc5  push    r15
0x18000cbc7  sub     rsp, 30h
0x18000cbcb  mov     r15, rdx
0x18000cbce  mov     rdi, rcx
0x18000cbd1  xor     ebx, ebx
0x18000cbd3  mov     [rsp+58h+arg_8], rbx
0x18000cbd8  test    rdx, rdx
0x18000cbdb  jz      short loc_18000CC0E
0x18000cbdd  mov     rax, 1FFFFFFFFFFFFFFFh
0x18000cbe7  cmp     rdx, rax
0x18000cbea  ja      loc_18000CC90
0x18000cbf0  lea     rcx, ds:0[rdx*8]; Size
0x18000cbf8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cbfd  mov     rbx, rax
0x18000cc00  mov     [rsp+58h+arg_8], rax
0x18000cc05  test    rax, rax
0x18000cc08  jz      loc_18000CC90
0x18000cc0e  lea     rsi, [rdi+8]
0x18000cc12  mov     r8, rbx
0x18000cc15  mov     rdx, [rsi]
0x18000cc18  mov     rcx, [rdi]
0x18000cc1b  call    ??$_Uninit_move@PEAV?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@PEAV12@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@@std@@V12@@std@@YAPEAV?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@PEAV12@00AEAU?$_Wrap_alloc@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy> *,wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>,wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>(wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy> *,wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy> *,wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy> *,std::_Wrap_alloc<std::allocator<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>> &,wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy> *,std::_Nonscalar_ptr_iterator_tag)
0x18000cc20  nop
0x18000cc21  mov     r14, [rdi]
0x18000cc24  mov     r13, [rsi]
0x18000cc27  mov     r12, r13
0x18000cc2a  sub     r12, r14
0x18000cc2d  sar     r12, 3
0x18000cc31  test    r14, r14
0x18000cc34  jz      short loc_18000CC66
0x18000cc36  cmp     r14, r13
0x18000cc39  jz      short loc_18000CC5D
0x18000cc3b  mov     rcx, [r14]
0x18000cc3e  test    rcx, rcx
0x18000cc41  jz      short loc_18000CC50
0x18000cc43  mov     rax, [rcx]
0x18000cc46  mov     rax, [rax+10h]
0x18000cc4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc4f  nop
0x18000cc50  add     r14, 8
0x18000cc54  cmp     r14, r13
0x18000cc57  jnz     short loc_18000CC3B
0x18000cc59  lea     rsi, [rdi+8]
0x18000cc5d  mov     rcx, [rdi]
0x18000cc60  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cc66  lea     rax, [rbx+r15*8]
0x18000cc6a  mov     [rdi+10h], rax
0x18000cc6e  lea     rax, [rbx+r12*8]
0x18000cc72  mov     [rsi], rax
0x18000cc75  mov     [rdi], rbx
0x18000cc78  mov     rbx, [rsp+58h+arg_0]
0x18000cc7d  mov     rsi, [rsp+58h+arg_10]
0x18000cc82  add     rsp, 30h
0x18000cc86  pop     r15
0x18000cc88  pop     r14
0x18000cc8a  pop     r13
0x18000cc8c  pop     r12
0x18000cc8e  pop     rdi
0x18000cc8f  retn
0x18000cc90  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
