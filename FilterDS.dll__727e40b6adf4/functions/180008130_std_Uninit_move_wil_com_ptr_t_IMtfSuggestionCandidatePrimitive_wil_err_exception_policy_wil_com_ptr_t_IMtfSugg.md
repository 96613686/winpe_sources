# std::_Uninit_move<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy> *,wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>,wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>(wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy> *,wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy> *,wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy> *,std::_Wrap_alloc<std::allocator<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>> &,wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x180008130`
- end: `0x18000816c`
- name: `??$_Uninit_move@PEAV?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@PEAV12@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@@std@@V12@@std@@YAPEAV?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@PEAV12@00AEAU?$_Wrap_alloc@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `60`
- prototype: `_QWORD *__fastcall(__int64 *, __int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cbb4`

## callees

- `0x180008130`

## pseudocode

```c
_QWORD *__fastcall std::_Uninit_move<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy> *,wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>,wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>(
        __int64 *a1,
        __int64 *a2,
        _QWORD *a3)
{
  __int64 v3; // rax

  while ( a1 != a2 )
  {
    v3 = *a1;
    *a1 = 0;
    *a3++ = v3;
    ++a1;
  }
  return a3;
}

```

## disassembly

```asm
0x180008130  mov     [rsp+arg_18], r9
0x180008135  mov     [rsp+arg_10], r8
0x18000813a  sub     rsp, 28h
0x18000813e  mov     [rsp+28h+arg_18], r8
0x180008143  jmp     short loc_18000815F
0x180008145  mov     rax, [rcx]
0x180008148  mov     qword ptr [rcx], 0
0x18000814f  mov     [r8], rax
0x180008152  add     r8, 8
0x180008156  mov     [rsp+28h+arg_10], r8
0x18000815b  add     rcx, 8
0x18000815f  cmp     rcx, rdx
0x180008162  jnz     short loc_180008145
0x180008164  mov     rax, r8
0x180008167  add     rsp, 28h
0x18000816b  retn
```
