# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001738`
- end: `0x1800017cf`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800017d8`
- `0x180001820`
- `0x1800018cc`
- `0x18000192c`
- `0x1800019a0`
- `0x180001a34`
- `0x18000d4f4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800017c4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800017c4`

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
0x180001738  sub     rsp, 48h
0x18000173c  movzx   eax, byte ptr [rdx]
0x18000173f  mov     r11, rcx
0x180001742  shl     eax, 18h
0x180001745  mov     r10, r8
0x180001748  mov     r8, [rsp+48h+arg_28]
0x18000174d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001751  movzx   eax, word ptr [rdx+1]
0x180001755  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001759  mov     rax, [rdx+3]
0x18000175d  add     rdx, 0Bh
0x180001761  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001766  mov     rax, [rcx+8]
0x18000176a  mov     [r8], rax
0x18000176d  mov     rax, [rcx+8]
0x180001771  mov     [rsp+48h+UserData], r8; UserData
0x180001776  movzx   ecx, word ptr [rax]
0x180001779  mov     [r8+8], ecx
0x18000177d  lea     rcx, _TraceLoggingMetadata
0x180001784  mov     [r8+10h], rdx
0x180001788  mov     dword ptr [r8+0Ch], 2
0x180001790  movzx   eax, word ptr [rdx]
0x180001793  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001798  mov     [r8+18h], eax
0x18000179c  lea     rax, _TraceLoggingMetadataEnd
0x1800017a3  sub     eax, ecx
0x1800017a5  mov     dword ptr [r8+1Ch], 1
0x1800017ad  mov     dword ptr [rsp+48h+arg_28], eax
0x1800017b1  mov     r8, r10; ActivityId
0x1800017b4  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800017b8  mov     eax, [rsp+48h+arg_20]
0x1800017bc  mov     rcx, [r11+20h]; RegHandle
0x1800017c0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800017c4  call    cs:__imp_EventWriteTransfer
0x1800017ca  add     rsp, 48h
0x1800017ce  retn
```
