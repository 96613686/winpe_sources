# ATL::CComCachedTearOffObject<CImpIRowsetInfo>::`scalar deleting destructor'(uint)

- ea: `0x18000a88c`
- end: `0x18000a8b0`
- name: `??_G?$CComCachedTearOffObject@VCImpIRowsetInfo@@@ATL@@QEAAPEAXI@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b490`
- `0x18000c6f0`

## callees

- `0x180001dd8`
- `0x18000a3f4`
- `0x18000a88c`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIRowsetInfo>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIRowsetInfo>::~CComCachedTearOffObject<CImpIRowsetInfo>((__int64)a1);
  if ( a1 )
    MMMFree(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a88c  push    rbx
0x18000a88e  sub     rsp, 20h
0x18000a892  mov     rbx, rcx
0x18000a895  call    ??1?$CComCachedTearOffObject@VCImpIRowsetInfo@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIRowsetInfo>::~CComCachedTearOffObject<CImpIRowsetInfo>(void)
0x18000a89a  test    rbx, rbx
0x18000a89d  jz      short loc_18000A8A7
0x18000a89f  mov     rcx, rbx; unsigned __int8 *
0x18000a8a2  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18000a8a7  mov     rax, rbx
0x18000a8aa  add     rsp, 20h
0x18000a8ae  pop     rbx
0x18000a8af  retn
```
