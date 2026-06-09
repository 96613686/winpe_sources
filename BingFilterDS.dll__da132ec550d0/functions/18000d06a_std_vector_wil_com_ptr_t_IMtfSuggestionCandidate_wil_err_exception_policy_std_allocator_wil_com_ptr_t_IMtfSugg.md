# _std::vector_wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy__std::allocator_wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy_____::_Reallocate_::_1_::catch$1

- ea: `0x18000d06a`
- end: `0x18000d08a`
- name: `_std::vector_wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy__std::allocator_wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy_____::_Reallocate_::_1_::catch$1`
- size: `32`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000274c`
- `0x18000ab2c`

## pseudocode

```c
void __fastcall __noreturn std::vector_wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy__std::allocator_wil::com_ptr_t_IMtfSuggestionCandidate_wil::err_exception_policy_____::_Reallocate_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  std::_Tree_buy<std::wstring>::_Freenode0(a1, *(void **)(a2 + 104));
  throw;
}

```

## disassembly

```asm
0x18000d06a  mov     [rsp+arg_8], rdx
0x18000d06f  push    rbp
0x18000d070  sub     rsp, 30h
0x18000d074  mov     rbp, rdx
0x18000d077  mov     rdx, [rbp+68h]
0x18000d07b  call    ?_Freenode0@?$_Tree_buy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXPEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@@Z; std::_Tree_buy<std::wstring>::_Freenode0(std::_Tree_node<std::wstring,void *> *)
0x18000d080  xor     edx, edx; pThrowInfo
0x18000d082  xor     ecx, ecx; pExceptionObject
0x18000d084  call    _CxxThrowException_0
```
