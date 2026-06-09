# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001108`
- end: `0x1800011a6`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `31`
- callee_count: `0`
- tags: ``

## callers

- `0x180001090`
- `0x1800011ac`
- `0x180001258`
- `0x180001320`
- `0x1800094c8`
- `0x18000aa50`
- `0x18000ab50`
- `0x18000ba80`
- `0x18000bb30`
- `0x18000bf10`
- `0x18000d194`
- `0x18000e09c`
- `0x18000ebe8`
- `0x18000ef14`
- `0x18000f818`
- `0x18000fecc`
- `0x180010cd0`
- `0x180012670`
- `0x180013274`
- `0x180013408`
- `0x1800134d0`
- `0x1800137d8`
- `0x180013cd0`
- `0x180013e08`
- `0x180013eac`
- `0x180013f4c`
- `0x180014ab4`
- `0x180018d90`
- `0x18001a570`
- `0x18001ae3c`
- `0x180021250`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001194`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001194`

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
0x180001108  sub     rsp, 48h
0x18000110c  movzx   eax, byte ptr [rdx]
0x18000110f  mov     r11, rcx
0x180001112  shl     eax, 18h
0x180001115  mov     r10, r8
0x180001118  mov     r8, [rsp+48h+arg_28]
0x18000111d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001121  movzx   eax, word ptr [rdx+1]
0x180001125  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001129  mov     rax, [rdx+3]
0x18000112d  add     rdx, 0Bh
0x180001131  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001136  mov     rax, [rcx+8]
0x18000113a  mov     [r8], rax
0x18000113d  mov     rax, [rcx+8]
0x180001141  mov     [rsp+48h+UserData], r8; UserData
0x180001146  movzx   ecx, word ptr [rax]
0x180001149  mov     [r8+8], ecx
0x18000114d  lea     rcx, _TraceLoggingMetadata
0x180001154  mov     [r8+10h], rdx
0x180001158  mov     dword ptr [r8+0Ch], 2
0x180001160  movzx   eax, word ptr [rdx]
0x180001163  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001168  mov     [r8+18h], eax
0x18000116c  lea     rax, _TraceLoggingMetadataEnd
0x180001173  sub     eax, ecx
0x180001175  mov     dword ptr [r8+1Ch], 1
0x18000117d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001181  mov     r8, r10; ActivityId
0x180001184  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001188  mov     eax, [rsp+48h+arg_20]
0x18000118c  mov     rcx, [r11+20h]; RegHandle
0x180001190  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001194  call    cs:__imp_EventWriteTransfer
0x18000119b  nop     dword ptr [rax+rax+00h]
0x1800011a0  add     rsp, 48h
0x1800011a4  retn
```
