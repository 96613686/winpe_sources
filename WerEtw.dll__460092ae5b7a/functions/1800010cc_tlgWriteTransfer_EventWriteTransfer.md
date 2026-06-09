# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800010cc`
- end: `0x180001163`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x180006dc0`
- `0x180008290`
- `0x180008a88`
- `0x18000f5dc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001158`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001158`

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
0x1800010cc  sub     rsp, 48h
0x1800010d0  movzx   eax, byte ptr [rdx]
0x1800010d3  mov     r11, rcx
0x1800010d6  shl     eax, 18h
0x1800010d9  mov     r10, r8
0x1800010dc  mov     r8, [rsp+48h+arg_28]
0x1800010e1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800010e5  movzx   eax, word ptr [rdx+1]
0x1800010e9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800010ed  mov     rax, [rdx+3]
0x1800010f1  add     rdx, 0Bh
0x1800010f5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800010fa  mov     rax, [rcx+8]
0x1800010fe  mov     [r8], rax
0x180001101  mov     rax, [rcx+8]
0x180001105  mov     [rsp+48h+UserData], r8; UserData
0x18000110a  movzx   ecx, word ptr [rax]
0x18000110d  mov     [r8+8], ecx
0x180001111  lea     rcx, _TraceLoggingMetadata
0x180001118  mov     [r8+10h], rdx
0x18000111c  mov     dword ptr [r8+0Ch], 2
0x180001124  movzx   eax, word ptr [rdx]
0x180001127  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000112c  mov     [r8+18h], eax
0x180001130  lea     rax, _TraceLoggingMetadataEnd
0x180001137  sub     eax, ecx
0x180001139  mov     dword ptr [r8+1Ch], 1
0x180001141  mov     dword ptr [rsp+48h+arg_28], eax
0x180001145  mov     r8, r10; ActivityId
0x180001148  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000114c  mov     eax, [rsp+48h+arg_20]
0x180001150  mov     rcx, [r11+20h]; RegHandle
0x180001154  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001158  call    cs:__imp_EventWriteTransfer
0x18000115e  add     rsp, 48h
0x180001162  retn
```
