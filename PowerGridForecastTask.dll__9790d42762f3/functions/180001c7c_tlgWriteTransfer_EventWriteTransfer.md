# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001c7c`
- end: `0x180001d13`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800012e0`
- `0x1800013a4`
- `0x180001658`
- `0x1800018fc`
- `0x180027a1c`
- `0x180029c00`
- `0x18002e574`
- `0x18002e778`
- `0x18002e980`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001d08`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001d08`

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
0x180001c7c  sub     rsp, 48h
0x180001c80  movzx   eax, byte ptr [rdx]
0x180001c83  mov     r11, rcx
0x180001c86  shl     eax, 18h
0x180001c89  mov     r10, r8
0x180001c8c  mov     r8, [rsp+48h+arg_28]
0x180001c91  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001c95  movzx   eax, word ptr [rdx+1]
0x180001c99  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001c9d  mov     rax, [rdx+3]
0x180001ca1  add     rdx, 0Bh
0x180001ca5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001caa  mov     rax, [rcx+8]
0x180001cae  mov     [r8], rax
0x180001cb1  mov     rax, [rcx+8]
0x180001cb5  mov     [rsp+48h+UserData], r8; UserData
0x180001cba  movzx   ecx, word ptr [rax]
0x180001cbd  mov     [r8+8], ecx
0x180001cc1  lea     rcx, _TraceLoggingMetadata
0x180001cc8  mov     [r8+10h], rdx
0x180001ccc  mov     dword ptr [r8+0Ch], 2
0x180001cd4  movzx   eax, word ptr [rdx]
0x180001cd7  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001cdc  mov     [r8+18h], eax
0x180001ce0  lea     rax, _TraceLoggingMetadataEnd
0x180001ce7  sub     eax, ecx
0x180001ce9  mov     dword ptr [r8+1Ch], 1
0x180001cf1  mov     dword ptr [rsp+48h+arg_28], eax
0x180001cf5  mov     r8, r10; ActivityId
0x180001cf8  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001cfc  mov     eax, [rsp+48h+arg_20]
0x180001d00  mov     rcx, [r11+20h]; RegHandle
0x180001d04  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001d08  call    cs:__imp_EventWriteTransfer
0x180001d0e  add     rsp, 48h
0x180001d12  retn
```
