# HCI_Destroy(HCI_INTERFACE *)

- ea: `0x140073d88`
- end: `0x140073f3f`
- name: `?HCI_Destroy@@YAXPEAUHCI_INTERFACE@@@Z`
- size: `439`
- prototype: `void __fastcall(struct HCI_INTERFACE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140077690`

## callees

- `0x140005b4c`
- `0x1400234e0`
- `0x140073d88`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140073f2c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140073f2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073df1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073e16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073e3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073e60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073e85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073eb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073df1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073e16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073e3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073e60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073e85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073eb4`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140073efd`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140073efd`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140073ed9`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140073ed9`

## pseudocode

```c
void __fastcall HCI_Destroy(struct HCI_INTERFACE *a1)
{
  bool v2; // dl
  _ULARGE_INTEGER *StoredLinkKeyCodMasks; // rcx
  _ULARGE_INTEGER *SlaveRoleCodMasks; // rcx
  unsigned __int16 *GuaranteedPsms; // rcx
  unsigned __int8 *EirReservedIds; // rcx
  void *SupportedCodecResult; // rcx
  unsigned __int8 *EventPrefix; // rcx
  __int64 Default; // rax
  RECORDER_LOG__ *IfrLog; // rdx

  v2 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_q(
    WPP_GLOBAL_Control->AttachedDevice,
    v2,
    1,
    a1->IfrLog,
    4,
    6,
    16,
    (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids,
    (char)a1);
  StoredLinkKeyCodMasks = a1->StoredLinkKeyCodMasks;
  if ( StoredLinkKeyCodMasks )
  {
    ExFreePoolWithTag(StoredLinkKeyCodMasks, 0);
    a1->StoredLinkKeyCodMasks = 0;
  }
  SlaveRoleCodMasks = a1->SlaveRoleCodMasks;
  if ( SlaveRoleCodMasks )
  {
    ExFreePoolWithTag(SlaveRoleCodMasks, 0);
    a1->SlaveRoleCodMasks = 0;
  }
  GuaranteedPsms = a1->GuaranteedPsms;
  if ( GuaranteedPsms )
  {
    ExFreePoolWithTag(GuaranteedPsms, 0);
    a1->GuaranteedPsms = 0;
  }
  EirReservedIds = a1->EirInfo.EirReservedIds;
  if ( EirReservedIds )
  {
    ExFreePoolWithTag(EirReservedIds, 0);
    a1->EirInfo.EirReservedIds = 0;
  }
  SupportedCodecResult = a1->SupportedCodecResult;
  if ( SupportedCodecResult )
  {
    ExFreePoolWithTag(SupportedCodecResult, 0);
    a1->SupportedCodecResultSize = 0;
    a1->SupportedCodecResult = 0;
  }
  EventPrefix = a1->VsMsftInfo.EventPrefix;
  if ( EventPrefix )
  {
    ExFreePoolWithTag(EventPrefix, 0);
    a1->VsMsftInfo.EventPrefix = 0;
    a1->VsMsftInfo.EventPrefixLength = 0;
  }
  Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
  IfrLog = a1->IfrLog;
  if ( IfrLog && IfrLog != (RECORDER_LOG__ *)Default )
    imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
  a1->IfrLog = 0;
  DeviceException_Cleanup(a1);
  if ( a1->LookasideListInitialized )
    ExDeleteNPagedLookasideList(&a1->WritePacketLookasideList);
}

```

## disassembly

```asm
0x140073d88  push    rbx
0x140073d8a  sub     rsp, 50h
0x140073d8e  mov     rbx, rcx
0x140073d91  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140073d98  mov     eax, [rcx+2Ch]
0x140073d9b  test    al, 20h
0x140073d9d  jz      short loc_140073DA9
0x140073d9f  cmp     byte ptr [rcx+29h], 4
0x140073da3  jb      short loc_140073DA9
0x140073da5  mov     dl, 1
0x140073da7  jmp     short loc_140073DAB
0x140073da9  xor     dl, dl
0x140073dab  mov     r9, [rbx+10B0h]
0x140073db2  lea     rax, WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids
0x140073db9  mov     rcx, [rcx+18h]
0x140073dbd  mov     r8b, 1
0x140073dc0  mov     [rsp+58h+var_18], rbx
0x140073dc5  mov     [rsp+58h+var_20], rax
0x140073dca  mov     [rsp+58h+var_28], 10h
0x140073dd1  mov     [rsp+58h+var_30], 6
0x140073dd9  mov     [rsp+58h+var_38], 4
0x140073dde  call    WPP_RECORDER_AND_TRACE_SF_q
0x140073de3  mov     rcx, [rbx+0BD8h]; P
0x140073dea  test    rcx, rcx
0x140073ded  jz      short loc_140073E08
0x140073def  xor     edx, edx; Tag
0x140073df1  call    cs:__imp_ExFreePoolWithTag
0x140073df8  nop     dword ptr [rax+rax+00h]
0x140073dfd  mov     qword ptr [rbx+0BD8h], 0
0x140073e08  mov     rcx, [rbx+0BE8h]; P
0x140073e0f  test    rcx, rcx
0x140073e12  jz      short loc_140073E2D
0x140073e14  xor     edx, edx; Tag
0x140073e16  call    cs:__imp_ExFreePoolWithTag
0x140073e1d  nop     dword ptr [rax+rax+00h]
0x140073e22  mov     qword ptr [rbx+0BE8h], 0
0x140073e2d  mov     rcx, [rbx+0D50h]; P
0x140073e34  test    rcx, rcx
0x140073e37  jz      short loc_140073E52
0x140073e39  xor     edx, edx; Tag
0x140073e3b  call    cs:__imp_ExFreePoolWithTag
0x140073e42  nop     dword ptr [rax+rax+00h]
0x140073e47  mov     qword ptr [rbx+0D50h], 0
0x140073e52  mov     rcx, [rbx+3A0h]; P
0x140073e59  test    rcx, rcx
0x140073e5c  jz      short loc_140073E77
0x140073e5e  xor     edx, edx; Tag
0x140073e60  call    cs:__imp_ExFreePoolWithTag
0x140073e67  nop     dword ptr [rax+rax+00h]
0x140073e6c  mov     qword ptr [rbx+3A0h], 0
0x140073e77  mov     rcx, [rbx+0F50h]; P
0x140073e7e  test    rcx, rcx
0x140073e81  jz      short loc_140073EA6
0x140073e83  xor     edx, edx; Tag
0x140073e85  call    cs:__imp_ExFreePoolWithTag
0x140073e8c  nop     dword ptr [rax+rax+00h]
0x140073e91  mov     dword ptr [rbx+0F48h], 0
0x140073e9b  mov     qword ptr [rbx+0F50h], 0
0x140073ea6  mov     rcx, [rbx+1038h]; P
0x140073ead  test    rcx, rcx
0x140073eb0  jz      short loc_140073ED2
0x140073eb2  xor     edx, edx; Tag
0x140073eb4  call    cs:__imp_ExFreePoolWithTag
0x140073ebb  nop     dword ptr [rax+rax+00h]
0x140073ec0  mov     qword ptr [rbx+1038h], 0
0x140073ecb  mov     byte ptr [rbx+1034h], 0
0x140073ed2  mov     rcx, cs:WPP_GLOBAL_Control
0x140073ed9  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140073ee0  nop     dword ptr [rax+rax+00h]
0x140073ee5  mov     rdx, [rbx+10B0h]
0x140073eec  test    rdx, rdx
0x140073eef  jz      short loc_140073F09
0x140073ef1  cmp     rdx, rax
0x140073ef4  jz      short loc_140073F09
0x140073ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x140073efd  call    cs:__imp_imp_WppRecorderLogDelete
0x140073f04  nop     dword ptr [rax+rax+00h]
0x140073f09  mov     rcx, rbx; struct HCI_INTERFACE *
0x140073f0c  mov     qword ptr [rbx+10B0h], 0
0x140073f17  call    ?DeviceException_Cleanup@@YAXPEAUHCI_INTERFACE@@@Z; DeviceException_Cleanup(HCI_INTERFACE *)
0x140073f1c  cmp     byte ptr [rbx+0D18h], 0
0x140073f23  jz      short loc_140073F38
0x140073f25  lea     rcx, [rbx+0A00h]; Lookaside
0x140073f2c  call    cs:__imp_ExDeleteNPagedLookasideList
0x140073f33  nop     dword ptr [rax+rax+00h]
0x140073f38  add     rsp, 50h
0x140073f3c  pop     rbx
0x140073f3d  retn
```
