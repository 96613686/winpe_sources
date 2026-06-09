# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800017d8`
- end: `0x18000186f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180001358`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001864`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001864`

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
0x1800017d8  sub     rsp, 48h
0x1800017dc  movzx   eax, byte ptr [rdx]
0x1800017df  mov     r11, rcx
0x1800017e2  shl     eax, 18h
0x1800017e5  mov     r10, r8
0x1800017e8  mov     r8, [rsp+48h+arg_28]
0x1800017ed  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800017f1  movzx   eax, word ptr [rdx+1]
0x1800017f5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800017f9  mov     rax, [rdx+3]
0x1800017fd  add     rdx, 0Bh
0x180001801  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001806  mov     rax, [rcx+8]
0x18000180a  mov     [r8], rax
0x18000180d  mov     rax, [rcx+8]
0x180001811  mov     [rsp+48h+UserData], r8; UserData
0x180001816  movzx   ecx, word ptr [rax]
0x180001819  mov     [r8+8], ecx
0x18000181d  lea     rcx, _TraceLoggingMetadata
0x180001824  mov     [r8+10h], rdx
0x180001828  mov     dword ptr [r8+0Ch], 2
0x180001830  movzx   eax, word ptr [rdx]
0x180001833  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001838  mov     [r8+18h], eax
0x18000183c  lea     rax, _TraceLoggingMetadataEnd
0x180001843  sub     eax, ecx
0x180001845  mov     dword ptr [r8+1Ch], 1
0x18000184d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001851  mov     r8, r10; ActivityId
0x180001854  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001858  mov     eax, [rsp+48h+arg_20]
0x18000185c  mov     rcx, [r11+20h]; RegHandle
0x180001860  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001864  call    cs:__imp_EventWriteTransfer
0x18000186a  add     rsp, 48h
0x18000186e  retn
```
