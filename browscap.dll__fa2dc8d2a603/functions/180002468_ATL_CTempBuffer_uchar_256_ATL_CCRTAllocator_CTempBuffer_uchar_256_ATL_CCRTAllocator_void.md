# ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)

- ea: `0x180002468`
- end: `0x18000247f`
- name: `??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bb42`
- `0x18000bb66`
- `0x18000bcad`

## callees

- `0x180002468`
- `0x180003ea4`

## pseudocode

```c
__int64 __fastcall ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(
        _QWORD *a1)
{
  __int64 result; // rax

  result = (__int64)(a1 + 1);
  if ( (_QWORD *)*a1 != a1 + 1 )
    return ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(a1);
  return result;
}

```

## disassembly

```asm
0x180002468  sub     rsp, 28h
0x18000246c  lea     rax, [rcx+8]
0x180002470  cmp     [rcx], rax
0x180002473  jz      short loc_18000247A
0x180002475  call    ?FreeHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000247a  add     rsp, 28h
0x18000247e  retn
```
