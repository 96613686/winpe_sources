# ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::`scalar deleting destructor'(uint)

- ea: `0x18000a7dc`
- end: `0x18000a800`
- name: `??_G?$CComCachedTearOffObject@VCImpIColumnsUpdateInfo@@@ATL@@QEAAPEAXI@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000b0c0`
- `0x18000c5f0`

## callees

- `0x180001dd8`
- `0x18000a368`
- `0x18000a7dc`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::~CComCachedTearOffObject<CImpIColumnsUpdateInfo>((__int64)a1);
  if ( a1 )
    MMMFree(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a7dc  push    rbx
0x18000a7de  sub     rsp, 20h
0x18000a7e2  mov     rbx, rcx
0x18000a7e5  call    ??1?$CComCachedTearOffObject@VCImpIColumnsUpdateInfo@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::~CComCachedTearOffObject<CImpIColumnsUpdateInfo>(void)
0x18000a7ea  test    rbx, rbx
0x18000a7ed  jz      short loc_18000A7F7
0x18000a7ef  mov     rcx, rbx; unsigned __int8 *
0x18000a7f2  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18000a7f7  mov     rax, rbx
0x18000a7fa  add     rsp, 20h
0x18000a7fe  pop     rbx
0x18000a7ff  retn
```
