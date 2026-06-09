# ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)

- ea: `0x140002708`
- end: `0x14000271f`
- name: `??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140011ff0`
- `0x140012002`
- `0x140012082`

## callees

- `0x140002708`
- `0x140003d60`

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
0x140002708  sub     rsp, 28h
0x14000270c  lea     rax, [rcx+8]
0x140002710  cmp     [rcx], rax
0x140002713  jz      short loc_14000271A
0x140002715  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x14000271a  add     rsp, 28h
0x14000271e  retn
```
