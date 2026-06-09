# _std::_Uninit_move_wil::com_ptr_t_IMtfSuggestionCandidatePrimitive_wil::err_exception_policy____wil::com_ptr_t_IMtfSuggestionCandidatePrimitive_wil::err_exception_policy____std::allocator_wil::com_ptr_t_IMtfSuggestionCandidatePrimitive_wil::err_exception_policy____wil::com_ptr_t_IMtfSuggestionCandidatePrimitive_wil::err_exception_policy____::_1_::catch$0

- ea: `0x1800220d8`
- end: `0x180022108`
- name: `_std::_Uninit_move_wil::com_ptr_t_IMtfSuggestionCandidatePrimitive_wil::err_exception_policy____wil::com_ptr_t_IMtfSuggestionCandidatePrimitive_wil::err_exception_policy____std::allocator_wil::com_ptr_t_IMtfSuggestionCandidatePrimitive_wil::err_exception_policy____wil::com_ptr_t_IMtfSuggestionCandidatePrimitive_wil::err_exception_policy____::_1_::catch$0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000230c`
- `0x180008174`
- `0x1800220d8`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_wil::com_ptr_t_IMtfSuggestionCandidatePrimitive_wil::err_exception_policy____wil::com_ptr_t_IMtfSuggestionCandidatePrimitive_wil::err_exception_policy____std::allocator_wil::com_ptr_t_IMtfSuggestionCandidatePrimitive_wil::err_exception_policy____wil::com_ptr_t_IMtfSuggestionCandidatePrimitive_wil::err_exception_policy____::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  _QWORD *i; // rbx

  for ( i = *(_QWORD **)(a2 + 72); i != *(_QWORD **)(a2 + 64); ++i )
    std::_Wrap_alloc<std::allocator<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>>::destroy<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>(
      a1,
      i);
  throw;
}

```

## disassembly

```asm
0x1800220d8  mov     [rsp+arg_8], rdx
0x1800220dd  push    rbx
0x1800220de  push    rbp
0x1800220df  sub     rsp, 28h
0x1800220e3  mov     rbp, rdx
0x1800220e6  mov     rbx, [rbp+48h]
0x1800220ea  jmp     short loc_1800220F8
0x1800220ec  mov     rdx, rbx
0x1800220ef  call    ??$destroy@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@@?$_Wrap_alloc@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAAXPEAV?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@@Z; std::_Wrap_alloc<std::allocator<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>>::destroy<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>(wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy> *)
0x1800220f4  add     rbx, 8
0x1800220f8  cmp     rbx, [rbp+40h]
0x1800220fc  jnz     short loc_1800220EC
0x1800220fe  xor     edx, edx; pThrowInfo
0x180022100  xor     ecx, ecx; pExceptionObject
0x180022102  call    _CxxThrowException_0
```
