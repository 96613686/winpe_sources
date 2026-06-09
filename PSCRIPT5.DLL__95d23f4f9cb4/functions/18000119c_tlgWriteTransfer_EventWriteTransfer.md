# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000119c`
- end: `0x180001233`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000123c`
- `0x180001314`
- `0x1800015c8`
- `0x180009ee4`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180001228`
- `ADVAPI32!EventWriteTransfer` at `0x180001228`

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
0x18000119c  sub     rsp, 48h
0x1800011a0  movzx   eax, byte ptr [rdx]
0x1800011a3  mov     r11, rcx
0x1800011a6  shl     eax, 18h
0x1800011a9  mov     r10, r8
0x1800011ac  mov     r8, [rsp+48h+arg_28]
0x1800011b1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800011b5  movzx   eax, word ptr [rdx+1]
0x1800011b9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800011bd  mov     rax, [rdx+3]
0x1800011c1  add     rdx, 0Bh
0x1800011c5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800011ca  mov     rax, [rcx+8]
0x1800011ce  mov     [r8], rax
0x1800011d1  mov     rax, [rcx+8]
0x1800011d5  mov     [rsp+48h+UserData], r8; UserData
0x1800011da  movzx   ecx, word ptr [rax]
0x1800011dd  mov     [r8+8], ecx
0x1800011e1  lea     rcx, _TraceLoggingMetadata
0x1800011e8  mov     [r8+10h], rdx
0x1800011ec  mov     dword ptr [r8+0Ch], 2
0x1800011f4  movzx   eax, word ptr [rdx]
0x1800011f7  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800011fc  mov     [r8+18h], eax
0x180001200  lea     rax, _TraceLoggingMetadataEnd
0x180001207  sub     eax, ecx
0x180001209  mov     dword ptr [r8+1Ch], 1
0x180001211  mov     dword ptr [rsp+48h+arg_28], eax
0x180001215  mov     r8, r10; ActivityId
0x180001218  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000121c  mov     eax, [rsp+48h+arg_20]
0x180001220  mov     rcx, [r11+20h]; RegHandle
0x180001224  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001228  call    cs:__imp_EventWriteTransfer
0x18000122e  add     rsp, 48h
0x180001232  retn
```
