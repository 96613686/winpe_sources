# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001008`
- end: `0x1400010ac`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `164`
- prototype: `__int64 __fastcall(int, int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `69`
- callee_count: `0`
- tags: ``

## callers

- `0x1400010c0`
- `0x140001460`
- `0x140001870`
- `0x140003640`
- `0x1400039dc`
- `0x140003d14`
- `0x140003e40`
- `0x14000411c`
- `0x140004364`
- `0x140004fc0`
- `0x140005138`
- `0x140005424`
- `0x1400055d8`
- `0x140005d4c`
- `0x1400061a0`
- `0x140006630`
- `0x140006810`
- `0x140007044`
- `0x140007250`
- `0x14000748c`
- `0x140007890`
- `0x140007b60`
- `0x140007e5c`
- `0x140008598`
- `0x140008d3c`
- `0x140009390`
- `0x140009530`
- `0x14000995c`
- `0x140009b9c`
- `0x14000a3a0`
- `0x14000a4bc`
- `0x14000a7a0`
- `0x14000aa50`
- `0x14000accc`
- `0x14000af40`
- `0x14000b4c4`
- `0x14000b7bc`
- `0x14000bf64`
- `0x14000c434`
- `0x14000c658`
- `0x14000c9a4`
- `0x14000cd20`
- `0x14000d140`
- `0x14000d3f8`
- `0x14000d5a0`
- `0x14000d848`
- `0x14000dadc`
- `0x14000e110`
- `0x14000e560`
- `0x14000e848`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000109a`
- `ntoskrnl!EtwWriteTransfer` at `0x14000109a`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteTransfer_EtwWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  ULONGLONG v6; // rax
  unsigned __int16 *v7; // rdx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v6;
  UserData->Ptr = (ULONGLONG)EventInformation;
  UserData->Size = *(unsigned __int16 *)EventInformation;
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData->Reserved = 2;
  UserData[1].Size = *v7;
  UserData[1].Reserved = 1;
  return EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, UserData);
}

```

## disassembly

```asm
0x140001008  sub     rsp, 48h
0x14000100c  movzx   eax, byte ptr [rdx]
0x14000100f  xor     r9d, r9d; RelatedActivityId
0x140001012  mov     r8, [rsp+48h+arg_28]
0x140001017  shl     eax, 18h
0x14000101a  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x14000101e  movzx   eax, word ptr [rdx+1]
0x140001022  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001026  mov     rax, [rdx+3]
0x14000102a  add     rdx, 0Bh
0x14000102e  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001033  mov     rax, cs:EventInformation
0x14000103a  mov     [r8], rax
0x14000103d  mov     rax, cs:EventInformation
0x140001044  mov     [rsp+48h+UserData], r8; UserData
0x140001049  mov     [rsp+48h+UserDataCount], 3; UserDataCount
0x140001051  movzx   ecx, word ptr [rax]
0x140001054  mov     [r8+8], ecx
0x140001058  lea     rcx, _TraceLoggingMetadata
0x14000105f  mov     [r8+10h], rdx
0x140001063  mov     dword ptr [r8+0Ch], 2
0x14000106b  movzx   eax, word ptr [rdx]
0x14000106e  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001073  mov     [r8+18h], eax
0x140001077  lea     rax, _TraceLoggingMetadataEnd
0x14000107e  sub     eax, ecx
0x140001080  mov     dword ptr [r8+1Ch], 1
0x140001088  mov     [rsp+48h+arg_20], eax
0x14000108c  xor     r8d, r8d; ActivityId
0x14000108f  mov     eax, [rsp+48h+arg_20]
0x140001093  mov     rcx, cs:RegHandle; RegHandle
0x14000109a  call    cs:__imp_EtwWriteTransfer
0x1400010a1  nop     dword ptr [rax+rax+00h]
0x1400010a6  add     rsp, 48h
0x1400010aa  retn
```
