# _ON_CREATE_PROC_DATA::_ON_CREATE_PROC_DATA_::_1_::dtor$6

- ea: `0x18000c619`
- end: `0x18000c625`
- name: `_ON_CREATE_PROC_DATA::_ON_CREATE_PROC_DATA_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180006190`

## pseudocode

```c
__int64 __fastcall ON_CREATE_PROC_DATA::_ON_CREATE_PROC_DATA_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(*(_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x18000c619  mov     rcx, [rdx+30h]
0x18000c620  jmp     ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
```
