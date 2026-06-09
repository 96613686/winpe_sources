# _AppPrioritizationUserSession::GetProcessNameFromProcessId_::_1_::dtor$0

- ea: `0x18000c495`
- end: `0x18000c4a1`
- name: `_AppPrioritizationUserSession::GetProcessNameFromProcessId_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180008960`

## pseudocode

```c
__int64 __fastcall AppPrioritizationUserSession::GetProcessNameFromProcessId_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(a2 + 104);
}

```

## disassembly

```asm
0x18000c495  lea     rcx, [rdx+68h]
0x18000c49c  jmp     ??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
```
