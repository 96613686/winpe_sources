# _ATL::CRegObject::AddReplacement_::_1_::dtor$0

- ea: `0x180024dcc`
- end: `0x180024dd8`
- name: `_ATL::CRegObject::AddReplacement_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001f40`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::AddReplacement_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(a2 + 32);
}

```

## disassembly

```asm
0x180024dcc  lea     rcx, [rdx+20h]
0x180024dd3  jmp     ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
```
