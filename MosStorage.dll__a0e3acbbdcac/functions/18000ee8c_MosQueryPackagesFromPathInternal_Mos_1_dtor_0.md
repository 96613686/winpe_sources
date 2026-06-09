# _MosQueryPackagesFromPathInternal_Mos_::_1_::dtor$0

- ea: `0x18000ee8c`
- end: `0x18000ee98`
- name: `_MosQueryPackagesFromPathInternal_Mos_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000ae44`

## pseudocode

```c
__int64 __fastcall MosQueryPackagesFromPathInternal_Mos_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>>(a2 + 72);
}

```

## disassembly

```asm
0x18000ee8c  lea     rcx, [rdx+48h]
0x18000ee93  jmp     ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>>(void)
```
