# _StartList::CreateATProcess_::_1_::dtor$1

- ea: `0x140015d84`
- end: `0x140015d90`
- name: `_StartList::CreateATProcess_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003728`

## pseudocode

```c
__int64 __fastcall StartList::CreateATProcess_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::~CHeapPtr<unsigned short,ATL::CCRTAllocator>(a2 + 72);
}

```

## disassembly

```asm
0x140015d84  lea     rcx, [rdx+48h]
0x140015d8b  jmp     ??1?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::~CHeapPtr<ushort,ATL::CCRTAllocator>(void)
```
