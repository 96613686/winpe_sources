# ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)

- ea: `0x1800035c8`
- end: `0x1800035df`
- name: `??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ce11`
- `0x18000ce23`
- `0x18000ceb5`

## callees

- `0x1800035c8`
- `0x1800050f8`

## pseudocode

```c
__int64 __fastcall ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(
        _QWORD *a1)
{
  __int64 result; // rax

  result = (__int64)(a1 + 1);
  if ( (_QWORD *)*a1 != a1 + 1 )
    return ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(a1);
  return result;
}

```

## disassembly

```asm
0x1800035c8  sub     rsp, 28h
0x1800035cc  lea     rax, [rcx+8]
0x1800035d0  cmp     [rcx], rax
0x1800035d3  jz      short loc_1800035DA
0x1800035d5  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800035da  add     rsp, 28h
0x1800035de  retn
```
