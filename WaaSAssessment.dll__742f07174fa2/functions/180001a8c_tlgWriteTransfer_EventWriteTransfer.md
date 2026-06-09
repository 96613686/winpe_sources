# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001a8c`
- end: `0x180001b23`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800012e0`
- `0x1800013a4`
- `0x180001658`
- `0x180001b2c`
- `0x180001bbc`
- `0x180001d00`
- `0x180011b50`
- `0x1800170c8`
- `0x180017244`
- `0x18001752c`
- `0x1800176a4`
- `0x1800177f0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001b18`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001b18`

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
0x180001a8c  sub     rsp, 48h
0x180001a90  movzx   eax, byte ptr [rdx]
0x180001a93  mov     r11, rcx
0x180001a96  shl     eax, 18h
0x180001a99  mov     r10, r8
0x180001a9c  mov     r8, [rsp+48h+arg_28]
0x180001aa1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001aa5  movzx   eax, word ptr [rdx+1]
0x180001aa9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001aad  mov     rax, [rdx+3]
0x180001ab1  add     rdx, 0Bh
0x180001ab5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001aba  mov     rax, [rcx+8]
0x180001abe  mov     [r8], rax
0x180001ac1  mov     rax, [rcx+8]
0x180001ac5  mov     [rsp+48h+UserData], r8; UserData
0x180001aca  movzx   ecx, word ptr [rax]
0x180001acd  mov     [r8+8], ecx
0x180001ad1  lea     rcx, _TraceLoggingMetadata
0x180001ad8  mov     [r8+10h], rdx
0x180001adc  mov     dword ptr [r8+0Ch], 2
0x180001ae4  movzx   eax, word ptr [rdx]
0x180001ae7  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001aec  mov     [r8+18h], eax
0x180001af0  lea     rax, _TraceLoggingMetadataEnd
0x180001af7  sub     eax, ecx
0x180001af9  mov     dword ptr [r8+1Ch], 1
0x180001b01  mov     dword ptr [rsp+48h+arg_28], eax
0x180001b05  mov     r8, r10; ActivityId
0x180001b08  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001b0c  mov     eax, [rsp+48h+arg_20]
0x180001b10  mov     rcx, [r11+20h]; RegHandle
0x180001b14  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001b18  call    cs:__imp_EventWriteTransfer
0x180001b1e  add     rsp, 48h
0x180001b22  retn
```
