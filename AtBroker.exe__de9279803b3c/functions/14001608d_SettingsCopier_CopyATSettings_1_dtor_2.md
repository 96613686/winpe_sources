# _SettingsCopier::CopyATSettings_::_1_::dtor$2

- ea: `0x14001608d`
- end: `0x140016099`
- name: `_SettingsCopier::CopyATSettings_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140011c38`

## pseudocode

```c
__int64 __fastcall SettingsCopier::CopyATSettings_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CHeapPtr<unsigned char,ATL::CCRTAllocator>::~CHeapPtr<unsigned char,ATL::CCRTAllocator>(a2 + 72);
}

```

## disassembly

```asm
0x14001608d  lea     rcx, [rdx+48h]
0x140016094  jmp     ??1?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CHeapPtr<uchar,ATL::CCRTAllocator>::~CHeapPtr<uchar,ATL::CCRTAllocator>(void)
```
