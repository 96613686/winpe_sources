# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001130`
- end: `0x1400011c7`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x140001098`
- `0x14000124c`
- `0x14000132c`
- `0x140001424`
- `0x140003210`
- `0x140003ce4`
- `0x1400059ac`
- `0x14000a3d4`
- `0x14000aae8`
- `0x14000ac60`
- `0x14000b454`
- `0x14000ca40`
- `0x14000cf10`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400011bc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400011bc`

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
0x140001130  sub     rsp, 48h
0x140001134  movzx   eax, byte ptr [rdx]
0x140001137  mov     r11, rcx
0x14000113a  shl     eax, 18h
0x14000113d  mov     r10, r8
0x140001140  mov     r8, [rsp+48h+arg_28]
0x140001145  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001149  movzx   eax, word ptr [rdx+1]
0x14000114d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001151  mov     rax, [rdx+3]
0x140001155  add     rdx, 0Bh
0x140001159  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x14000115e  mov     rax, [rcx+8]
0x140001162  mov     [r8], rax
0x140001165  mov     rax, [rcx+8]
0x140001169  mov     [rsp+48h+UserData], r8; UserData
0x14000116e  movzx   ecx, word ptr [rax]
0x140001171  mov     [r8+8], ecx
0x140001175  lea     rcx, _TraceLoggingMetadata
0x14000117c  mov     [r8+10h], rdx
0x140001180  mov     dword ptr [r8+0Ch], 2
0x140001188  movzx   eax, word ptr [rdx]
0x14000118b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001190  mov     [r8+18h], eax
0x140001194  lea     rax, _TraceLoggingMetadataEnd
0x14000119b  sub     eax, ecx
0x14000119d  mov     dword ptr [r8+1Ch], 1
0x1400011a5  mov     dword ptr [rsp+48h+arg_28], eax
0x1400011a9  mov     r8, r10; ActivityId
0x1400011ac  mov     eax, dword ptr [rsp+48h+arg_28]
0x1400011b0  mov     eax, [rsp+48h+arg_20]
0x1400011b4  mov     rcx, [r11+20h]; RegHandle
0x1400011b8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400011bc  call    cs:__imp_EventWriteTransfer
0x1400011c2  add     rsp, 48h
0x1400011c6  retn
```
