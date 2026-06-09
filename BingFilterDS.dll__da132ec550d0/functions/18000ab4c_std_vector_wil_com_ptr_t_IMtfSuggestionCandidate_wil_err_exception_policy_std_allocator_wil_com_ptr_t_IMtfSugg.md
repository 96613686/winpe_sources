# std::vector<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>>::_Reallocate(unsigned __int64)

- ea: `0x18000ab4c`
- end: `0x18000ac2e`
- name: `?_Reallocate@?$vector@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@IEAAX_K@Z`
- size: `226`
- prototype: `__int64 *__fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000a180`

## callees

- `0x180001da8`
- `0x180001fa8`
- `0x1800086d8`
- `0x18000ab4c`
- `0x18000e010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000abf8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000abf8`

## pseudocode

```c
__int64 *__fastcall std::vector<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>::_Reallocate(
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
  void *v11; // [rsp+68h] [rbp+10h]

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
    std::_Uninit_move<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *,wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>,wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>(
      *(__int64 **)a1,
      *(__int64 **)(a1 + 8),
      v4);
  }
  catch ( ... )
  {
    std::_Tree_buy<std::wstring>::_Freenode0(v5, v11);
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
0x18000ab4c  mov     [rsp+arg_0], rbx
0x18000ab51  mov     [rsp+arg_10], rsi
0x18000ab56  push    rdi
0x18000ab57  push    r12
0x18000ab59  push    r13
0x18000ab5b  push    r14
0x18000ab5d  push    r15
0x18000ab5f  sub     rsp, 30h
0x18000ab63  mov     r15, rdx
0x18000ab66  mov     rdi, rcx
0x18000ab69  xor     ebx, ebx
0x18000ab6b  mov     [rsp+58h+arg_8], rbx
0x18000ab70  test    rdx, rdx
0x18000ab73  jz      short loc_18000ABA6
0x18000ab75  mov     rax, 1FFFFFFFFFFFFFFFh
0x18000ab7f  cmp     rdx, rax
0x18000ab82  ja      loc_18000AC28
0x18000ab88  lea     rcx, ds:0[rdx*8]; Size
0x18000ab90  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ab95  mov     rbx, rax
0x18000ab98  mov     [rsp+58h+arg_8], rax
0x18000ab9d  test    rax, rax
0x18000aba0  jz      loc_18000AC28
0x18000aba6  lea     rsi, [rdi+8]
0x18000abaa  mov     r8, rbx
0x18000abad  mov     rdx, [rsi]
0x18000abb0  mov     rcx, [rdi]
0x18000abb3  call    ??$_Uninit_move@PEAV?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@PEAV12@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@@std@@V12@@std@@YAPEAV?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@PEAV12@00AEAU?$_Wrap_alloc@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *,wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>,wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>(wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *,wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *,wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *,std::_Wrap_alloc<std::allocator<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>> &,wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *,std::_Nonscalar_ptr_iterator_tag)
0x18000abb8  nop
0x18000abb9  mov     r14, [rdi]
0x18000abbc  mov     r13, [rsi]
0x18000abbf  mov     r12, r13
0x18000abc2  sub     r12, r14
0x18000abc5  sar     r12, 3
0x18000abc9  test    r14, r14
0x18000abcc  jz      short loc_18000ABFE
0x18000abce  cmp     r14, r13
0x18000abd1  jz      short loc_18000ABF5
0x18000abd3  mov     rcx, [r14]
0x18000abd6  test    rcx, rcx
0x18000abd9  jz      short loc_18000ABE8
0x18000abdb  mov     rax, [rcx]
0x18000abde  mov     rax, [rax+10h]
0x18000abe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abe7  nop
0x18000abe8  add     r14, 8
0x18000abec  cmp     r14, r13
0x18000abef  jnz     short loc_18000ABD3
0x18000abf1  lea     rsi, [rdi+8]
0x18000abf5  mov     rcx, [rdi]
0x18000abf8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000abfe  lea     rax, [rbx+r15*8]
0x18000ac02  mov     [rdi+10h], rax
0x18000ac06  lea     rax, [rbx+r12*8]
0x18000ac0a  mov     [rsi], rax
0x18000ac0d  mov     [rdi], rbx
0x18000ac10  mov     rbx, [rsp+58h+arg_0]
0x18000ac15  mov     rsi, [rsp+58h+arg_10]
0x18000ac1a  add     rsp, 30h
0x18000ac1e  pop     r15
0x18000ac20  pop     r14
0x18000ac22  pop     r13
0x18000ac24  pop     r12
0x18000ac26  pop     rdi
0x18000ac27  retn
0x18000ac28  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
