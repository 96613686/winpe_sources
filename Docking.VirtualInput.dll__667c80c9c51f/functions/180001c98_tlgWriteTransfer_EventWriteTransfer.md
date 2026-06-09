# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001c98`
- end: `0x180001d2f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800012e0`
- `0x1800013b4`
- `0x180001478`
- `0x180001734`
- `0x180002900`
- `0x18000298c`
- `0x180002a48`
- `0x180002bdc`
- `0x180002c84`
- `0x180002d34`
- `0x180002e00`
- `0x180002fe0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001d24`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001d24`

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
0x180001c98  sub     rsp, 48h
0x180001c9c  movzx   eax, byte ptr [rdx]
0x180001c9f  mov     r11, rcx
0x180001ca2  shl     eax, 18h
0x180001ca5  mov     r10, r8
0x180001ca8  mov     r8, [rsp+48h+arg_28]
0x180001cad  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001cb1  movzx   eax, word ptr [rdx+1]
0x180001cb5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001cb9  mov     rax, [rdx+3]
0x180001cbd  add     rdx, 0Bh
0x180001cc1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001cc6  mov     rax, [rcx+8]
0x180001cca  mov     [r8], rax
0x180001ccd  mov     rax, [rcx+8]
0x180001cd1  mov     [rsp+48h+UserData], r8; UserData
0x180001cd6  movzx   ecx, word ptr [rax]
0x180001cd9  mov     [r8+8], ecx
0x180001cdd  lea     rcx, _TraceLoggingMetadata
0x180001ce4  mov     [r8+10h], rdx
0x180001ce8  mov     dword ptr [r8+0Ch], 2
0x180001cf0  movzx   eax, word ptr [rdx]
0x180001cf3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001cf8  mov     [r8+18h], eax
0x180001cfc  lea     rax, _TraceLoggingMetadataEnd
0x180001d03  sub     eax, ecx
0x180001d05  mov     dword ptr [r8+1Ch], 1
0x180001d0d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001d11  mov     r8, r10; ActivityId
0x180001d14  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001d18  mov     eax, [rsp+48h+arg_20]
0x180001d1c  mov     rcx, [r11+20h]; RegHandle
0x180001d20  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001d24  call    cs:__imp_EventWriteTransfer
0x180001d2a  add     rsp, 48h
0x180001d2e  retn
```
