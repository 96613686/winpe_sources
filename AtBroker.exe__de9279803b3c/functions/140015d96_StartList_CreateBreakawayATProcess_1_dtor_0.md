# _StartList::CreateBreakawayATProcess_::_1_::dtor$0

- ea: `0x140015d96`
- end: `0x140015da2`
- name: `_StartList::CreateBreakawayATProcess_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003728`

## pseudocode

```c
__int64 __fastcall StartList::CreateBreakawayATProcess_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::~CHeapPtr<unsigned short,ATL::CCRTAllocator>(a2 + 104);
}

```

## disassembly

```asm
0x140015d96  lea     rcx, [rdx+68h]
0x140015d9d  jmp     ??1?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::~CHeapPtr<ushort,ATL::CCRTAllocator>(void)
```
