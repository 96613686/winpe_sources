# _SettingsCopier::OpenSessionKey_::_1_::dtor$1

- ea: `0x14001609f`
- end: `0x1400160ab`
- name: `_SettingsCopier::OpenSessionKey_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140003728`

## pseudocode

```c
__int64 __fastcall SettingsCopier::OpenSessionKey_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::~CHeapPtr<unsigned short,ATL::CCRTAllocator>(a2 + 64);
}

```

## disassembly

```asm
0x14001609f  lea     rcx, [rdx+40h]
0x1400160a6  jmp     ??1?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::~CHeapPtr<ushort,ATL::CCRTAllocator>(void)
```
