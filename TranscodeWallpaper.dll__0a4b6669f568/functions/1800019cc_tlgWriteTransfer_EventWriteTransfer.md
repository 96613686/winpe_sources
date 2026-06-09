# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800019cc`
- end: `0x180001a63`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800012e0`
- `0x1800013a4`
- `0x180001658`
- `0x180008220`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001a58`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001a58`

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
0x1800019cc  sub     rsp, 48h
0x1800019d0  movzx   eax, byte ptr [rdx]
0x1800019d3  mov     r11, rcx
0x1800019d6  shl     eax, 18h
0x1800019d9  mov     r10, r8
0x1800019dc  mov     r8, [rsp+48h+arg_28]
0x1800019e1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800019e5  movzx   eax, word ptr [rdx+1]
0x1800019e9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800019ed  mov     rax, [rdx+3]
0x1800019f1  add     rdx, 0Bh
0x1800019f5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800019fa  mov     rax, [rcx+8]
0x1800019fe  mov     [r8], rax
0x180001a01  mov     rax, [rcx+8]
0x180001a05  mov     [rsp+48h+UserData], r8; UserData
0x180001a0a  movzx   ecx, word ptr [rax]
0x180001a0d  mov     [r8+8], ecx
0x180001a11  lea     rcx, _TraceLoggingMetadata
0x180001a18  mov     [r8+10h], rdx
0x180001a1c  mov     dword ptr [r8+0Ch], 2
0x180001a24  movzx   eax, word ptr [rdx]
0x180001a27  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001a2c  mov     [r8+18h], eax
0x180001a30  lea     rax, _TraceLoggingMetadataEnd
0x180001a37  sub     eax, ecx
0x180001a39  mov     dword ptr [r8+1Ch], 1
0x180001a41  mov     dword ptr [rsp+48h+arg_28], eax
0x180001a45  mov     r8, r10; ActivityId
0x180001a48  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001a4c  mov     eax, [rsp+48h+arg_20]
0x180001a50  mov     rcx, [r11+20h]; RegHandle
0x180001a54  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001a58  call    cs:__imp_EventWriteTransfer
0x180001a5e  add     rsp, 48h
0x180001a62  retn
```
