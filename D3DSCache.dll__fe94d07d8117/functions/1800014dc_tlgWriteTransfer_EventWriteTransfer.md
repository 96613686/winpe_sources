# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800014dc`
- end: `0x180001573`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001568`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001568`

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
0x1800014dc  sub     rsp, 48h
0x1800014e0  movzx   eax, byte ptr [rdx]
0x1800014e3  mov     r11, rcx
0x1800014e6  shl     eax, 18h
0x1800014e9  mov     r10, r8
0x1800014ec  mov     r8, [rsp+48h+arg_28]
0x1800014f1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800014f5  movzx   eax, word ptr [rdx+1]
0x1800014f9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800014fd  mov     rax, [rdx+3]
0x180001501  add     rdx, 0Bh
0x180001505  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000150a  mov     rax, [rcx+8]
0x18000150e  mov     [r8], rax
0x180001511  mov     rax, [rcx+8]
0x180001515  mov     [rsp+48h+UserData], r8; UserData
0x18000151a  movzx   ecx, word ptr [rax]
0x18000151d  mov     [r8+8], ecx
0x180001521  lea     rcx, _TraceLoggingMetadata
0x180001528  mov     [r8+10h], rdx
0x18000152c  mov     dword ptr [r8+0Ch], 2
0x180001534  movzx   eax, word ptr [rdx]
0x180001537  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000153c  mov     [r8+18h], eax
0x180001540  lea     rax, _TraceLoggingMetadataEnd
0x180001547  sub     eax, ecx
0x180001549  mov     dword ptr [r8+1Ch], 1
0x180001551  mov     dword ptr [rsp+48h+arg_28], eax
0x180001555  mov     r8, r10; ActivityId
0x180001558  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000155c  mov     eax, [rsp+48h+arg_20]
0x180001560  mov     rcx, [r11+20h]; RegHandle
0x180001564  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001568  call    cs:__imp_EventWriteTransfer
0x18000156e  add     rsp, 48h
0x180001572  retn
```
