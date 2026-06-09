# ATL::CComCachedTearOffObject<CImpIColumnsRowset>::`scalar deleting destructor'(uint)

- ea: `0x18000a7b0`
- end: `0x18000a7d4`
- name: `??_G?$CComCachedTearOffObject@VCImpIColumnsRowset@@@ATL@@QEAAPEAXI@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000afe0`
- `0x18000c5b0`

## callees

- `0x180001dd8`
- `0x18000a344`
- `0x18000a7b0`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIColumnsRowset>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIColumnsRowset>::~CComCachedTearOffObject<CImpIColumnsRowset>((__int64)a1);
  if ( a1 )
    MMMFree(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a7b0  push    rbx
0x18000a7b2  sub     rsp, 20h
0x18000a7b6  mov     rbx, rcx
0x18000a7b9  call    ??1?$CComCachedTearOffObject@VCImpIColumnsRowset@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIColumnsRowset>::~CComCachedTearOffObject<CImpIColumnsRowset>(void)
0x18000a7be  test    rbx, rbx
0x18000a7c1  jz      short loc_18000A7CB
0x18000a7c3  mov     rcx, rbx; unsigned __int8 *
0x18000a7c6  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18000a7cb  mov     rax, rbx
0x18000a7ce  add     rsp, 20h
0x18000a7d2  pop     rbx
0x18000a7d3  retn
```
