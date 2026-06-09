# _std::_Uninit_move_wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy____wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy____std::allocator_wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy____wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy____::_1_::catch$0

- ea: `0x18000cd33`
- end: `0x18000cd63`
- name: `_std::_Uninit_move_wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy____wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy____std::allocator_wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy____wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy____::_1_::catch$0`
- size: `48`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000274c`
- `0x18000871c`
- `0x18000cd33`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy____wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy____std::allocator_wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy____wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy____::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  _QWORD *i; // rbx

  for ( i = *(_QWORD **)(a2 + 72); i != *(_QWORD **)(a2 + 64); ++i )
    std::_Wrap_alloc<std::allocator<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>>::destroy<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>(
      a1,
      i);
  throw;
}

```

## disassembly

```asm
0x18000cd33  mov     [rsp+arg_8], rdx
0x18000cd38  push    rbx
0x18000cd39  push    rbp
0x18000cd3a  sub     rsp, 28h
0x18000cd3e  mov     rbp, rdx
0x18000cd41  mov     rbx, [rbp+48h]
0x18000cd45  jmp     short loc_18000CD53
0x18000cd47  mov     rdx, rbx
0x18000cd4a  call    ??$destroy@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@@?$_Wrap_alloc@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAAXPEAV?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@@Z; std::_Wrap_alloc<std::allocator<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>>::destroy<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>(wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *)
0x18000cd4f  add     rbx, 8
0x18000cd53  cmp     rbx, [rbp+40h]
0x18000cd57  jnz     short loc_18000CD47
0x18000cd59  xor     edx, edx; pThrowInfo
0x18000cd5b  xor     ecx, ecx; pExceptionObject
0x18000cd5d  call    _CxxThrowException_0
```
