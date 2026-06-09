# _ATL::CAtlModule::UpdateRegistryFromResource_::_1_::dtor$23

- ea: `0x18000e85c`
- end: `0x18000e868`
- name: `_ATL::CAtlModule::UpdateRegistryFromResource_::_1_::dtor$23`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180003e74`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResource_::_1_::dtor_23(__int64 a1, __int64 a2)
{
  return ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(a2 + 88);
}

```

## disassembly

```asm
0x18000e85c  lea     rcx, [rdx+58h]
0x18000e863  jmp     ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
```
