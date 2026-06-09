# AiSvcOnCreateProcess$dtor$0

- ea: `0x18000c9e2`
- end: `0x18000c9ee`
- name: `AiSvcOnCreateProcess$dtor$0`
- size: `12`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800060fc`

## pseudocode

```c
int __fastcall AiSvcOnCreateProcess_dtor_0(__int64 a1, __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>((void **)(a2 + 144));
}

```

## disassembly

```asm
0x18000c9e2  lea     rcx, [rdx+90h]
0x18000c9e9  jmp     ??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
```
