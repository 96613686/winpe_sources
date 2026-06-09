# ATL::CComCachedTearOffObject<CImpIRowsetConnection>::`scalar deleting destructor'(uint)

- ea: `0x18000a860`
- end: `0x18000a884`
- name: `??_G?$CComCachedTearOffObject@VCImpIRowsetConnection@@@ATL@@QEAAPEAXI@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b3a0`
- `0x18000c6b0`

## callees

- `0x180001dd8`
- `0x18000a3d0`
- `0x18000a860`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIRowsetConnection>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIRowsetConnection>::~CComCachedTearOffObject<CImpIRowsetConnection>((__int64)a1);
  if ( a1 )
    MMMFree(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a860  push    rbx
0x18000a862  sub     rsp, 20h
0x18000a866  mov     rbx, rcx
0x18000a869  call    ??1?$CComCachedTearOffObject@VCImpIRowsetConnection@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIRowsetConnection>::~CComCachedTearOffObject<CImpIRowsetConnection>(void)
0x18000a86e  test    rbx, rbx
0x18000a871  jz      short loc_18000A87B
0x18000a873  mov     rcx, rbx; unsigned __int8 *
0x18000a876  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18000a87b  mov     rax, rbx
0x18000a87e  add     rsp, 20h
0x18000a882  pop     rbx
0x18000a883  retn
```
