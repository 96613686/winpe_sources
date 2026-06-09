# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001a4c`
- end: `0x180001ae3`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800010d0`
- `0x18000117c`
- `0x180001430`
- `0x1800016d4`
- `0x180004748`
- `0x18000ca14`
- `0x18000cc18`
- `0x18000ce20`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001ad8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001ad8`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_EventWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        ULONG UserDataCount,
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
  UserData->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData->Reserved = 2;
  UserData[1].Size = *v7;
  UserData[1].Reserved = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180001a4c  sub     rsp, 48h
0x180001a50  movzx   eax, byte ptr [rdx]
0x180001a53  mov     r11, rcx
0x180001a56  shl     eax, 18h
0x180001a59  mov     r10, r8
0x180001a5c  mov     r8, [rsp+48h+arg_28]
0x180001a61  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001a65  movzx   eax, word ptr [rdx+1]
0x180001a69  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001a6d  mov     rax, [rdx+3]
0x180001a71  add     rdx, 0Bh
0x180001a75  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001a7a  mov     rax, [rcx+8]
0x180001a7e  mov     [r8], rax
0x180001a81  mov     rax, [rcx+8]
0x180001a85  mov     [rsp+48h+UserData], r8; UserData
0x180001a8a  movzx   ecx, word ptr [rax]
0x180001a8d  mov     [r8+8], ecx
0x180001a91  lea     rcx, _TraceLoggingMetadata
0x180001a98  mov     [r8+10h], rdx
0x180001a9c  mov     dword ptr [r8+0Ch], 2
0x180001aa4  movzx   eax, word ptr [rdx]
0x180001aa7  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001aac  mov     [r8+18h], eax
0x180001ab0  lea     rax, _TraceLoggingMetadataEnd
0x180001ab7  sub     eax, ecx
0x180001ab9  mov     dword ptr [r8+1Ch], 1
0x180001ac1  mov     dword ptr [rsp+48h+arg_28], eax
0x180001ac5  mov     r8, r10; ActivityId
0x180001ac8  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001acc  mov     eax, [rsp+48h+arg_20]
0x180001ad0  mov     rcx, [r11+20h]; RegHandle
0x180001ad4  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001ad8  call    cs:__imp_EventWriteTransfer
0x180001ade  add     rsp, 48h
0x180001ae2  retn
```
