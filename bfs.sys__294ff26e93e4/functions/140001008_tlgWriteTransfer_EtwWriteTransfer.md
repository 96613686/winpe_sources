# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001008`
- end: `0x1400010ac`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `164`
- prototype: `__int64 __fastcall(int, int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `68`
- callee_count: `0`
- tags: ``

## callers

- `0x1400010c0`
- `0x140001460`
- `0x140003770`
- `0x140003b0c`
- `0x140003e44`
- `0x140003f70`
- `0x14000424c`
- `0x140004494`
- `0x140005150`
- `0x1400052c8`
- `0x1400055b4`
- `0x140005768`
- `0x140005edc`
- `0x140006330`
- `0x1400067c0`
- `0x1400069a0`
- `0x1400071d4`
- `0x1400073e0`
- `0x14000761c`
- `0x140007a20`
- `0x140007cf0`
- `0x140007fec`
- `0x140008728`
- `0x140008ecc`
- `0x140009520`
- `0x1400096c0`
- `0x140009aec`
- `0x140009d2c`
- `0x14000a530`
- `0x14000a64c`
- `0x14000a930`
- `0x14000abe0`
- `0x14000ae5c`
- `0x14000b0d0`
- `0x14000b654`
- `0x14000b94c`
- `0x14000c0f4`
- `0x14000c5c4`
- `0x14000c7e8`
- `0x14000cb34`
- `0x14000ceb4`
- `0x14000d2d4`
- `0x14000d58c`
- `0x14000d734`
- `0x14000d9dc`
- `0x14000dc70`
- `0x14000e2a0`
- `0x14000e6f0`
- `0x14000e9d8`
- `0x14000ed84`

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
