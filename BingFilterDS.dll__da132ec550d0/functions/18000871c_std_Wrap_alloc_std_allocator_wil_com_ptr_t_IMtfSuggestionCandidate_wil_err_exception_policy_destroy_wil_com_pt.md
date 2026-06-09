# std::_Wrap_alloc<std::allocator<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>>::destroy<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>(wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy> *)

- ea: `0x18000871c`
- end: `0x18000873a`
- name: `??$destroy@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@@?$_Wrap_alloc@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAAXPEAV?$com_ptr_t@UIMtfSuggestionCandidate@@Uerr_exception_policy@wil@@@wil@@@Z`
- size: `30`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cd33`

## callees

- `0x18000871c`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall std::_Wrap_alloc<std::allocator<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>>::destroy<wil::com_ptr_t<IMtfSuggestionCandidate,wil::err_exception_policy>>(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax

  if ( *a2 )
    return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
  return result;
}

```

## disassembly

```asm
0x18000871c  sub     rsp, 28h
0x180008720  mov     rcx, [rdx]
0x180008723  test    rcx, rcx
0x180008726  jz      short loc_180008735
0x180008728  mov     rax, [rcx]
0x18000872b  mov     rax, [rax+10h]
0x18000872f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008734  nop
0x180008735  add     rsp, 28h
0x180008739  retn
```
