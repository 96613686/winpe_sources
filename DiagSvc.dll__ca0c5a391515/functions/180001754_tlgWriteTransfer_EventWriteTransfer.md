# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001754`
- end: `0x1800017eb`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `20`
- callee_count: `0`
- tags: ``

## callers

- `0x180001178`
- `0x1800012b8`
- `0x18000140c`
- `0x180001570`
- `0x1800017f4`
- `0x180001b88`
- `0x180001d28`
- `0x180001e7c`
- `0x180001fec`
- `0x18000216c`
- `0x180002318`
- `0x180002498`
- `0x180002618`
- `0x1800027ac`
- `0x180002b78`
- `0x180002f88`
- `0x1800031e4`
- `0x180003378`
- `0x180003538`
- `0x18000374c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800017e0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800017e0`

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
0x180001754  sub     rsp, 48h
0x180001758  movzx   eax, byte ptr [rdx]
0x18000175b  mov     r11, rcx
0x18000175e  shl     eax, 18h
0x180001761  mov     r10, r8
0x180001764  mov     r8, [rsp+48h+arg_28]
0x180001769  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000176d  movzx   eax, word ptr [rdx+1]
0x180001771  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001775  mov     rax, [rdx+3]
0x180001779  add     rdx, 0Bh
0x18000177d  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001782  mov     rax, [rcx+8]
0x180001786  mov     [r8], rax
0x180001789  mov     rax, [rcx+8]
0x18000178d  mov     [rsp+48h+UserData], r8; UserData
0x180001792  movzx   ecx, word ptr [rax]
0x180001795  mov     [r8+8], ecx
0x180001799  lea     rcx, _TraceLoggingMetadata
0x1800017a0  mov     [r8+10h], rdx
0x1800017a4  mov     dword ptr [r8+0Ch], 2
0x1800017ac  movzx   eax, word ptr [rdx]
0x1800017af  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800017b4  mov     [r8+18h], eax
0x1800017b8  lea     rax, _TraceLoggingMetadataEnd
0x1800017bf  sub     eax, ecx
0x1800017c1  mov     dword ptr [r8+1Ch], 1
0x1800017c9  mov     dword ptr [rsp+48h+arg_28], eax
0x1800017cd  mov     r8, r10; ActivityId
0x1800017d0  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800017d4  mov     eax, [rsp+48h+arg_20]
0x1800017d8  mov     rcx, [r11+20h]; RegHandle
0x1800017dc  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800017e0  call    cs:__imp_EventWriteTransfer
0x1800017e6  add     rsp, 48h
0x1800017ea  retn
```
