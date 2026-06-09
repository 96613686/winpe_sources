# MpDlpShutdown

- ea: `0x140088a2c`
- end: `0x140088b3f`
- name: `MpDlpShutdown`
- size: `275`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14007bef0`
- `0x14008f314`
- `0x140094508`

## callees

- `0x140088a2c`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x140088afb`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140088b15`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140088afb`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140088b15`
- `ntoskrnl!ExUnregisterCallback` at `0x140088a4c`
- `ntoskrnl!ExUnregisterCallback` at `0x140088a4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088a8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088ab3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088b2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088a8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088ab3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140088b2d`
- `ntoskrnl!ObfDereferenceObject` at `0x140088a6b`
- `ntoskrnl!ObfDereferenceObject` at `0x140088a6b`
- `FLTMGR!FltDeletePushLock` at `0x140088acd`
- `FLTMGR!FltDeletePushLock` at `0x140088ae4`
- `FLTMGR!FltDeletePushLock` at `0x140088acd`
- `FLTMGR!FltDeletePushLock` at `0x140088ae4`

## pseudocode

```c
void MpDlpShutdown()
{
  void *v0; // rcx
  void *v1; // rcx
  void *v2; // rcx
  void *v3; // rcx

  if ( MpDlpData )
  {
    v0 = (void *)*((_QWORD *)MpDlpData + 39);
    if ( v0 )
      ExUnregisterCallback(v0);
    v1 = (void *)*((_QWORD *)MpDlpData + 38);
    if ( v1 )
      ObfDereferenceObject(v1);
    v2 = (void *)*((_QWORD *)MpDlpData + 35);
    if ( v2 )
      ExFreePoolWithTag(v2, 0x6E6F704Du);
    v3 = (void *)*((_QWORD *)MpDlpData + 36);
    if ( v3 )
      ExFreePoolWithTag(v3, 0x6E6F704Du);
    FltDeletePushLock((PULONG_PTR)MpDlpData + 31);
    FltDeletePushLock((PULONG_PTR)MpDlpData + 1);
    ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)((char *)MpDlpData + 48));
    ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)((char *)MpDlpData + 144));
    ExFreePoolWithTag(MpDlpData, 0x4464504Du);
  }
}

```

## disassembly

```asm
0x140088a2c  sub     rsp, 28h
0x140088a30  mov     rax, cs:MpDlpData
0x140088a37  test    rax, rax
0x140088a3a  jz      loc_140088B39
0x140088a40  mov     rcx, [rax+138h]; CallbackRegistration
0x140088a47  test    rcx, rcx
0x140088a4a  jz      short loc_140088A58
0x140088a4c  call    cs:__imp_ExUnregisterCallback
0x140088a53  nop     dword ptr [rax+rax+00h]
0x140088a58  mov     rax, cs:MpDlpData
0x140088a5f  mov     rcx, [rax+130h]; Object
0x140088a66  test    rcx, rcx
0x140088a69  jz      short loc_140088A77
0x140088a6b  call    cs:__imp_ObfDereferenceObject
0x140088a72  nop     dword ptr [rax+rax+00h]
0x140088a77  mov     rax, cs:MpDlpData
0x140088a7e  mov     rcx, [rax+118h]; P
0x140088a85  test    rcx, rcx
0x140088a88  jz      short loc_140088A9B
0x140088a8a  mov     edx, 6E6F704Dh; Tag
0x140088a8f  call    cs:__imp_ExFreePoolWithTag
0x140088a96  nop     dword ptr [rax+rax+00h]
0x140088a9b  mov     rax, cs:MpDlpData
0x140088aa2  mov     rcx, [rax+120h]; P
0x140088aa9  test    rcx, rcx
0x140088aac  jz      short loc_140088ABF
0x140088aae  mov     edx, 6E6F704Dh; Tag
0x140088ab3  call    cs:__imp_ExFreePoolWithTag
0x140088aba  nop     dword ptr [rax+rax+00h]
0x140088abf  mov     rcx, cs:MpDlpData
0x140088ac6  add     rcx, 0F8h; PushLock
0x140088acd  call    cs:__imp_FltDeletePushLock
0x140088ad4  nop     dword ptr [rax+rax+00h]
0x140088ad9  mov     rcx, cs:MpDlpData
0x140088ae0  add     rcx, 8; PushLock
0x140088ae4  call    cs:__imp_FltDeletePushLock
0x140088aeb  nop     dword ptr [rax+rax+00h]
0x140088af0  mov     rcx, cs:MpDlpData
0x140088af7  add     rcx, 30h ; '0'; Lookaside
0x140088afb  call    cs:__imp_ExDeleteLookasideListEx
0x140088b02  nop     dword ptr [rax+rax+00h]
0x140088b07  mov     rcx, cs:MpDlpData
0x140088b0e  add     rcx, 90h; Lookaside
0x140088b15  call    cs:__imp_ExDeleteLookasideListEx
0x140088b1c  nop     dword ptr [rax+rax+00h]
0x140088b21  mov     rcx, cs:MpDlpData; P
0x140088b28  mov     edx, 4464504Dh; Tag
0x140088b2d  call    cs:__imp_ExFreePoolWithTag
0x140088b34  nop     dword ptr [rax+rax+00h]
0x140088b39  add     rsp, 28h
0x140088b3d  retn
```
