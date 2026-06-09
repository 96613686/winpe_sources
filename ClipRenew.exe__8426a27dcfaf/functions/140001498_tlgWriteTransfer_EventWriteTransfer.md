# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001498`
- end: `0x14000152f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x14000108c`
- `0x140001150`
- `0x1400011e8`
- `0x1400012b0`
- `0x140001348`
- `0x1400013c4`
- `0x140005b30`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001524`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001524`

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
0x140001498  sub     rsp, 48h
0x14000149c  movzx   eax, byte ptr [rdx]
0x14000149f  mov     r11, rcx
0x1400014a2  shl     eax, 18h
0x1400014a5  mov     r10, r8
0x1400014a8  mov     r8, [rsp+48h+arg_28]
0x1400014ad  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1400014b1  movzx   eax, word ptr [rdx+1]
0x1400014b5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1400014b9  mov     rax, [rdx+3]
0x1400014bd  add     rdx, 0Bh
0x1400014c1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1400014c6  mov     rax, [rcx+8]
0x1400014ca  mov     [r8], rax
0x1400014cd  mov     rax, [rcx+8]
0x1400014d1  mov     [rsp+48h+UserData], r8; UserData
0x1400014d6  movzx   ecx, word ptr [rax]
0x1400014d9  mov     [r8+8], ecx
0x1400014dd  lea     rcx, _TraceLoggingMetadata
0x1400014e4  mov     [r8+10h], rdx
0x1400014e8  mov     dword ptr [r8+0Ch], 2
0x1400014f0  movzx   eax, word ptr [rdx]
0x1400014f3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1400014f8  mov     [r8+18h], eax
0x1400014fc  lea     rax, _TraceLoggingMetadataEnd
0x140001503  sub     eax, ecx
0x140001505  mov     dword ptr [r8+1Ch], 1
0x14000150d  mov     dword ptr [rsp+48h+arg_28], eax
0x140001511  mov     r8, r10; ActivityId
0x140001514  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001518  mov     eax, [rsp+48h+arg_20]
0x14000151c  mov     rcx, [r11+20h]; RegHandle
0x140001520  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001524  call    cs:__imp_EventWriteTransfer
0x14000152a  add     rsp, 48h
0x14000152e  retn
```
