# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001b78`
- end: `0x140001c0f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140001010`
- `0x1400012cc`
- `0x14000135c`
- `0x140001600`
- `0x1400018f8`
- `0x1400096a4`
- `0x14000dfdc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001c04`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001c04`

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
0x140001b78  sub     rsp, 48h
0x140001b7c  movzx   eax, byte ptr [rdx]
0x140001b7f  mov     r11, rcx
0x140001b82  shl     eax, 18h
0x140001b85  mov     r10, r8
0x140001b88  mov     r8, [rsp+48h+arg_28]
0x140001b8d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001b91  movzx   eax, word ptr [rdx+1]
0x140001b95  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001b99  mov     rax, [rdx+3]
0x140001b9d  add     rdx, 0Bh
0x140001ba1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001ba6  mov     rax, [rcx+8]
0x140001baa  mov     [r8], rax
0x140001bad  mov     rax, [rcx+8]
0x140001bb1  mov     [rsp+48h+UserData], r8; UserData
0x140001bb6  movzx   ecx, word ptr [rax]
0x140001bb9  mov     [r8+8], ecx
0x140001bbd  lea     rcx, _TraceLoggingMetadata
0x140001bc4  mov     [r8+10h], rdx
0x140001bc8  mov     dword ptr [r8+0Ch], 2
0x140001bd0  movzx   eax, word ptr [rdx]
0x140001bd3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001bd8  mov     [r8+18h], eax
0x140001bdc  lea     rax, _TraceLoggingMetadataEnd
0x140001be3  sub     eax, ecx
0x140001be5  mov     dword ptr [r8+1Ch], 1
0x140001bed  mov     dword ptr [rsp+48h+arg_28], eax
0x140001bf1  mov     r8, r10; ActivityId
0x140001bf4  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001bf8  mov     eax, [rsp+48h+arg_20]
0x140001bfc  mov     rcx, [r11+20h]; RegHandle
0x140001c00  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001c04  call    cs:__imp_EventWriteTransfer
0x140001c0a  add     rsp, 48h
0x140001c0e  retn
```
