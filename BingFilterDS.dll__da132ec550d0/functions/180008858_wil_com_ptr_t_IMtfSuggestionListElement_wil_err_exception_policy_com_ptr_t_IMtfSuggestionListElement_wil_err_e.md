# wil::com_ptr_t<IMtfSuggestionListElement,wil::err_exception_policy>::~com_ptr_t<IMtfSuggestionListElement,wil::err_exception_policy>(void)

- ea: `0x180008858`
- end: `0x180008876`
- name: `??1?$com_ptr_t@UIMtfSuggestionListElement@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cd69`
- `0x18000ce25`
- `0x18000ce5b`
- `0x18000ce6d`
- `0x18000ce7f`
- `0x18000ce91`
- `0x18000cf5c`
- `0x18000cf9c`
- `0x18000d058`

## callees

- `0x180008858`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IMtfSuggestionListElement,wil::err_exception_policy>::~com_ptr_t<IMtfSuggestionListElement,wil::err_exception_policy>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180008858  sub     rsp, 28h
0x18000885c  mov     rcx, [rcx]
0x18000885f  test    rcx, rcx
0x180008862  jz      short loc_180008871
0x180008864  mov     rax, [rcx]
0x180008867  mov     rax, [rax+10h]
0x18000886b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008870  nop
0x180008871  add     rsp, 28h
0x180008875  retn
```
