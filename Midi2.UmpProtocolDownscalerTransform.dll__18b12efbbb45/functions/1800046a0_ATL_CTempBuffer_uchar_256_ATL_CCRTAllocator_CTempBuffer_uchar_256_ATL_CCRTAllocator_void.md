# ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)

- ea: `0x1800046a0`
- end: `0x1800046b7`
- name: `??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180012304`
- `0x180012316`
- `0x1800123a8`

## callees

- `0x1800046a0`
- `0x1800061c8`

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
0x1800046a0  sub     rsp, 28h
0x1800046a4  lea     rax, [rcx+8]
0x1800046a8  cmp     [rcx], rax
0x1800046ab  jz      short loc_1800046B2
0x1800046ad  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800046b2  add     rsp, 28h
0x1800046b6  retn
```
