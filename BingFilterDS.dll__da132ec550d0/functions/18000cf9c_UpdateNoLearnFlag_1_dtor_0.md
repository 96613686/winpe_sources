# _UpdateNoLearnFlag_::_1_::dtor$0

- ea: `0x18000cf9c`
- end: `0x18000cfa8`
- name: `_UpdateNoLearnFlag_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180008858`

## pseudocode

```c
__int64 __fastcall UpdateNoLearnFlag_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IMtfSuggestionListElement,wil::err_exception_policy>::~com_ptr_t<IMtfSuggestionListElement,wil::err_exception_policy>((__int64 *)(a2 + 120));
}

```

## disassembly

```asm
0x18000cf9c  lea     rcx, [rdx+78h]
0x18000cfa3  jmp     ??1?$com_ptr_t@UIMtfSuggestionListElement@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMtfSuggestionListElement,wil::err_exception_policy>::~com_ptr_t<IMtfSuggestionListElement,wil::err_exception_policy>(void)
```
