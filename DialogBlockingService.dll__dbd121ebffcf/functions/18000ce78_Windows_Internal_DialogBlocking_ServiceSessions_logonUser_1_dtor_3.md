# _Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor$3

- ea: `0x18000ce78`
- end: `0x18000ce84`
- name: `_Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x18000890c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(a2 + 48);
}

```

## disassembly

```asm
0x18000ce78  lea     rcx, [rdx+30h]
0x18000ce7f  jmp     ??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
```
