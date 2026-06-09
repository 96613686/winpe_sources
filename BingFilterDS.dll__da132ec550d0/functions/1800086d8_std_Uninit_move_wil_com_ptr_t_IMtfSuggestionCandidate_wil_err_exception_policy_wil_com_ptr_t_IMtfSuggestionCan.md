# std::_Uninit_move<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *,wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>,wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>(wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *,wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *,wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *,std::_Wrap_alloc<std::allocator<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>> &,wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x1800086d8`
- end: `0x180008714`
- name: `??$_Uninit_move@PEAV?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@PEAV12@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@@std@@V12@@std@@YAPEAV?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@PEAV12@00AEAU?$_Wrap_alloc@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `60`
- prototype: `_QWORD *__fastcall(__int64 *, __int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ab4c`

## callees

- `0x1800086d8`

## pseudocode

```c
_QWORD *__fastcall std::_Uninit_move<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *,wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *,std::allocator<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>,wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>(
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
0x1800086d8  mov     [rsp+arg_18], r9
0x1800086dd  mov     [rsp+arg_10], r8
0x1800086e2  sub     rsp, 28h
0x1800086e6  mov     [rsp+28h+arg_18], r8
0x1800086eb  jmp     short loc_180008707
0x1800086ed  mov     rax, [rcx]
0x1800086f0  mov     qword ptr [rcx], 0
0x1800086f7  mov     [r8], rax
0x1800086fa  add     r8, 8
0x1800086fe  mov     [rsp+28h+arg_10], r8
0x180008703  add     rcx, 8
0x180008707  cmp     rcx, rdx
0x18000870a  jnz     short loc_1800086ED
0x18000870c  mov     rax, r8
0x18000870f  add     rsp, 28h
0x180008713  retn
```
