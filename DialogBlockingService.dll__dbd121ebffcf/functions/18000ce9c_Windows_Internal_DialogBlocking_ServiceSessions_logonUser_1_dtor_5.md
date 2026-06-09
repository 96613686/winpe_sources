# _Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor$5

- ea: `0x18000ce9c`
- end: `0x18000cea8`
- name: `_Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor$5`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800099b0`

## pseudocode

```c
void __fastcall Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>((void **)(a2 + 32));
}

```

## disassembly

```asm
0x18000ce9c  lea     rcx, [rdx+20h]
0x18000cea3  jmp     ??1?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(void)
```
