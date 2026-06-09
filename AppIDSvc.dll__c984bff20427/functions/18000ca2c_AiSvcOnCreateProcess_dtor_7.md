# AiSvcOnCreateProcess$dtor$7

- ea: `0x18000ca2c`
- end: `0x18000ca38`
- name: `AiSvcOnCreateProcess$dtor$7`
- size: `12`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180006190`

## pseudocode

```c
int __fastcall AiSvcOnCreateProcess_dtor_7(__int64 a1, __int64 a2)
{
  return wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((void **)(a2 + 144));
}

```

## disassembly

```asm
0x18000ca2c  lea     rcx, [rdx+90h]
0x18000ca33  jmp     ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
```
