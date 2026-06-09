# ATL::CComCachedTearOffObject<CImpIRowsetUpdate>::`scalar deleting destructor'(uint)

- ea: `0x18000a8b8`
- end: `0x18000a8dc`
- name: `??_G?$CComCachedTearOffObject@VCImpIRowsetUpdate@@@ATL@@QEAAPEAXI@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000b570`
- `0x18000c730`

## callees

- `0x180001dd8`
- `0x18000a418`
- `0x18000a8b8`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIRowsetUpdate>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIRowsetUpdate>::~CComCachedTearOffObject<CImpIRowsetUpdate>((__int64)a1);
  if ( a1 )
    MMMFree(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a8b8  push    rbx
0x18000a8ba  sub     rsp, 20h
0x18000a8be  mov     rbx, rcx
0x18000a8c1  call    ??1?$CComCachedTearOffObject@VCImpIRowsetUpdate@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIRowsetUpdate>::~CComCachedTearOffObject<CImpIRowsetUpdate>(void)
0x18000a8c6  test    rbx, rbx
0x18000a8c9  jz      short loc_18000A8D3
0x18000a8cb  mov     rcx, rbx; unsigned __int8 *
0x18000a8ce  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18000a8d3  mov     rax, rbx
0x18000a8d6  add     rsp, 20h
0x18000a8da  pop     rbx
0x18000a8db  retn
```
