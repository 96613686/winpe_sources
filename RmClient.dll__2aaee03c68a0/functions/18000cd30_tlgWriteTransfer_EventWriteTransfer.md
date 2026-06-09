# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000cd30`
- end: `0x18000cdc7`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180012170`
- `0x1800177d0`
- `0x1800178f0`
- `0x180019620`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cdbc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cdbc`

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
0x18000cd30  sub     rsp, 48h
0x18000cd34  movzx   eax, byte ptr [rdx]
0x18000cd37  mov     r11, rcx
0x18000cd3a  shl     eax, 18h
0x18000cd3d  mov     r10, r8
0x18000cd40  mov     r8, [rsp+48h+arg_28]
0x18000cd45  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000cd49  movzx   eax, word ptr [rdx+1]
0x18000cd4d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000cd51  mov     rax, [rdx+3]
0x18000cd55  add     rdx, 0Bh
0x18000cd59  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000cd5e  mov     rax, [rcx+8]
0x18000cd62  mov     [r8], rax
0x18000cd65  mov     rax, [rcx+8]
0x18000cd69  mov     [rsp+48h+UserData], r8; UserData
0x18000cd6e  movzx   ecx, word ptr [rax]
0x18000cd71  mov     [r8+8], ecx
0x18000cd75  lea     rcx, _TraceLoggingMetadata
0x18000cd7c  mov     [r8+10h], rdx
0x18000cd80  mov     dword ptr [r8+0Ch], 2
0x18000cd88  movzx   eax, word ptr [rdx]
0x18000cd8b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000cd90  mov     [r8+18h], eax
0x18000cd94  lea     rax, _TraceLoggingMetadataEnd
0x18000cd9b  sub     eax, ecx
0x18000cd9d  mov     dword ptr [r8+1Ch], 1
0x18000cda5  mov     dword ptr [rsp+48h+arg_28], eax
0x18000cda9  mov     r8, r10; ActivityId
0x18000cdac  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000cdb0  mov     eax, [rsp+48h+arg_20]
0x18000cdb4  mov     rcx, [r11+20h]; RegHandle
0x18000cdb8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000cdbc  call    cs:__imp_EventWriteTransfer
0x18000cdc2  add     rsp, 48h
0x18000cdc6  retn
```
