# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000125c`
- end: `0x1800012f3`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000108c`
- `0x18000116c`
- `0x180010920`
- `0x180010aac`
- `0x180010d48`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800012e8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800012e8`

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
0x18000125c  sub     rsp, 48h
0x180001260  movzx   eax, byte ptr [rdx]
0x180001263  mov     r11, rcx
0x180001266  shl     eax, 18h
0x180001269  mov     r10, r8
0x18000126c  mov     r8, [rsp+48h+arg_28]
0x180001271  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001275  movzx   eax, word ptr [rdx+1]
0x180001279  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000127d  mov     rax, [rdx+3]
0x180001281  add     rdx, 0Bh
0x180001285  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000128a  mov     rax, [rcx+8]
0x18000128e  mov     [r8], rax
0x180001291  mov     rax, [rcx+8]
0x180001295  mov     [rsp+48h+UserData], r8; UserData
0x18000129a  movzx   ecx, word ptr [rax]
0x18000129d  mov     [r8+8], ecx
0x1800012a1  lea     rcx, _TraceLoggingMetadata
0x1800012a8  mov     [r8+10h], rdx
0x1800012ac  mov     dword ptr [r8+0Ch], 2
0x1800012b4  movzx   eax, word ptr [rdx]
0x1800012b7  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800012bc  mov     [r8+18h], eax
0x1800012c0  lea     rax, _TraceLoggingMetadataEnd
0x1800012c7  sub     eax, ecx
0x1800012c9  mov     dword ptr [r8+1Ch], 1
0x1800012d1  mov     dword ptr [rsp+48h+arg_28], eax
0x1800012d5  mov     r8, r10; ActivityId
0x1800012d8  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800012dc  mov     eax, [rsp+48h+arg_20]
0x1800012e0  mov     rcx, [r11+20h]; RegHandle
0x1800012e4  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800012e8  call    cs:__imp_EventWriteTransfer
0x1800012ee  add     rsp, 48h
0x1800012f2  retn
```
