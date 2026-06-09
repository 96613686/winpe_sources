# _StartList::CreateBreakawayATProcess_::_1_::dtor$1

- ea: `0x140015da8`
- end: `0x140015db4`
- name: `_StartList::CreateBreakawayATProcess_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003728`

## pseudocode

```c
__int64 __fastcall StartList::CreateBreakawayATProcess_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::~CHeapPtr<unsigned short,ATL::CCRTAllocator>(a2 + 112);
}

```

## disassembly

```asm
0x140015da8  lea     rcx, [rdx+70h]
0x140015daf  jmp     ??1?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::~CHeapPtr<ushort,ATL::CCRTAllocator>(void)
```
