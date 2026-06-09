# ATL::CComCachedTearOffObject<CImpIColumnsInfo>::`scalar deleting destructor'(uint)

- ea: `0x18000a784`
- end: `0x18000a7a8`
- name: `??_G?$CComCachedTearOffObject@VCImpIColumnsInfo@@@ATL@@QEAAPEAXI@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000af00`
- `0x18000c570`

## callees

- `0x180001dd8`
- `0x18000a320`
- `0x18000a784`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIColumnsInfo>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIColumnsInfo>::~CComCachedTearOffObject<CImpIColumnsInfo>((__int64)a1);
  if ( a1 )
    MMMFree(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a784  push    rbx
0x18000a786  sub     rsp, 20h
0x18000a78a  mov     rbx, rcx
0x18000a78d  call    ??1?$CComCachedTearOffObject@VCImpIColumnsInfo@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIColumnsInfo>::~CComCachedTearOffObject<CImpIColumnsInfo>(void)
0x18000a792  test    rbx, rbx
0x18000a795  jz      short loc_18000A79F
0x18000a797  mov     rcx, rbx; unsigned __int8 *
0x18000a79a  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18000a79f  mov     rax, rbx
0x18000a7a2  add     rsp, 20h
0x18000a7a6  pop     rbx
0x18000a7a7  retn
```
