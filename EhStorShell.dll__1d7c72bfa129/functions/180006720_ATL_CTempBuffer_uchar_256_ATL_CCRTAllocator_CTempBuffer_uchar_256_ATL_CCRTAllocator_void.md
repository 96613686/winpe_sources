# ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)

- ea: `0x180006720`
- end: `0x180006737`
- name: `??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004710`
- `0x180007f20`
- `0x18000b946`
- `0x18000bd0e`

## callees

- `0x180006720`
- `0x180006740`

## pseudocode

```c
__int64 __fastcall ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(
        _QWORD *a1)
{
  __int64 result; // rax

  result = (__int64)(a1 + 1);
  if ( (_QWORD *)*a1 != a1 + 1 )
    return ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap();
  return result;
}

```

## disassembly

```asm
0x180006720  sub     rsp, 28h
0x180006724  lea     rax, [rcx+8]
0x180006728  cmp     [rcx], rax
0x18000672b  jz      short loc_180006732
0x18000672d  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180006732  add     rsp, 28h
0x180006736  retn
```
