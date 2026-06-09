# ATL::CComCachedTearOffObject<CImpIUpdateInfo>::`scalar deleting destructor'(uint)

- ea: `0x18000a8e4`
- end: `0x18000a908`
- name: `??_G?$CComCachedTearOffObject@VCImpIUpdateInfo@@@ATL@@QEAAPEAXI@Z`
- size: `36`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000b650`
- `0x18000c770`

## callees

- `0x180001dd8`
- `0x18000a43c`
- `0x18000a8e4`

## pseudocode

```c
unsigned __int8 *__fastcall ATL::CComCachedTearOffObject<CImpIUpdateInfo>::`scalar deleting destructor'(
        unsigned __int8 *a1)
{
  ATL::CComCachedTearOffObject<CImpIUpdateInfo>::~CComCachedTearOffObject<CImpIUpdateInfo>((__int64)a1);
  if ( a1 )
    MMMFree(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a8e4  push    rbx
0x18000a8e6  sub     rsp, 20h
0x18000a8ea  mov     rbx, rcx
0x18000a8ed  call    ??1?$CComCachedTearOffObject@VCImpIUpdateInfo@@@ATL@@QEAA@XZ; ATL::CComCachedTearOffObject<CImpIUpdateInfo>::~CComCachedTearOffObject<CImpIUpdateInfo>(void)
0x18000a8f2  test    rbx, rbx
0x18000a8f5  jz      short loc_18000A8FF
0x18000a8f7  mov     rcx, rbx; unsigned __int8 *
0x18000a8fa  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18000a8ff  mov     rax, rbx
0x18000a902  add     rsp, 20h
0x18000a906  pop     rbx
0x18000a907  retn
```
