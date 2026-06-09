# _ON_CREATE_PROC_DATA::_ON_CREATE_PROC_DATA_::_1_::dtor$0

- ea: `0x18000c62b`
- end: `0x18000c637`
- name: `_ON_CREATE_PROC_DATA::_ON_CREATE_PROC_DATA_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800060fc`

## pseudocode

```c
__int64 __fastcall ON_CREATE_PROC_DATA::_ON_CREATE_PROC_DATA_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(*(_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x18000c62b  mov     rcx, [rdx+30h]
0x18000c632  jmp     ??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
```
