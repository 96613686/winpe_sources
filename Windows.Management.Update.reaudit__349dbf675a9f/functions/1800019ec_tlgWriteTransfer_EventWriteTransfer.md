# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800019ec`
- end: `0x180001a8a`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800012e8`
- `0x1800013b0`
- `0x180001668`
- `0x18000b430`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001a78`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001a78`

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
0x1800019ec  sub     rsp, 48h
0x1800019f0  movzx   eax, byte ptr [rdx]
0x1800019f3  mov     r11, rcx
0x1800019f6  shl     eax, 18h
0x1800019f9  mov     r10, r8
0x1800019fc  mov     r8, [rsp+48h+arg_28]
0x180001a01  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001a05  movzx   eax, word ptr [rdx+1]
0x180001a09  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001a0d  mov     rax, [rdx+3]
0x180001a11  add     rdx, 0Bh
0x180001a15  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001a1a  mov     rax, [rcx+8]
0x180001a1e  mov     [r8], rax
0x180001a21  mov     rax, [rcx+8]
0x180001a25  mov     [rsp+48h+UserData], r8; UserData
0x180001a2a  movzx   ecx, word ptr [rax]
0x180001a2d  mov     [r8+8], ecx
0x180001a31  lea     rcx, _TraceLoggingMetadata
0x180001a38  mov     [r8+10h], rdx
0x180001a3c  mov     dword ptr [r8+0Ch], 2
0x180001a44  movzx   eax, word ptr [rdx]
0x180001a47  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001a4c  mov     [r8+18h], eax
0x180001a50  lea     rax, _TraceLoggingMetadataEnd
0x180001a57  sub     eax, ecx
0x180001a59  mov     dword ptr [r8+1Ch], 1
0x180001a61  mov     dword ptr [rsp+48h+arg_28], eax
0x180001a65  mov     r8, r10; ActivityId
0x180001a68  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001a6c  mov     eax, [rsp+48h+arg_20]
0x180001a70  mov     rcx, [r11+20h]; RegHandle
0x180001a74  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001a78  call    cs:__imp_EventWriteTransfer
0x180001a7f  nop     dword ptr [rax+rax+00h]
0x180001a84  add     rsp, 48h
0x180001a88  retn
```
