# _ATL::CAtlModule::UpdateRegistryFromResource_::_1_::dtor$1

- ea: `0x18000e880`
- end: `0x18000e88c`
- name: `_ATL::CAtlModule::UpdateRegistryFromResource_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180003e74`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResource_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(a2 + 96);
}

```

## disassembly

```asm
0x18000e880  lea     rcx, [rdx+60h]
0x18000e887  jmp     ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ
```
