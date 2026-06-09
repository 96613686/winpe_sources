# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800017b0`
- end: `0x180001847`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x18000116c`
- `0x1800012e0`
- `0x1800014ec`
- `0x1800016b0`
- `0x180001850`
- `0x1800018a0`
- `0x180001904`
- `0x1800019a0`
- `0x180001a4c`
- `0x180001b28`
- `0x180001bf4`
- `0x180001c6c`
- `0x18013699c`
- `0x18013d9e8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000183c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000183c`

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
0x1800017b0  sub     rsp, 48h
0x1800017b4  movzx   eax, byte ptr [rdx]
0x1800017b7  mov     r11, rcx
0x1800017ba  shl     eax, 18h
0x1800017bd  mov     r10, r8
0x1800017c0  mov     r8, [rsp+48h+arg_28]
0x1800017c5  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800017c9  movzx   eax, word ptr [rdx+1]
0x1800017cd  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800017d1  mov     rax, [rdx+3]
0x1800017d5  add     rdx, 0Bh
0x1800017d9  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800017de  mov     rax, [rcx+8]
0x1800017e2  mov     [r8], rax
0x1800017e5  mov     rax, [rcx+8]
0x1800017e9  mov     [rsp+48h+UserData], r8; UserData
0x1800017ee  movzx   ecx, word ptr [rax]
0x1800017f1  mov     [r8+8], ecx
0x1800017f5  lea     rcx, _TraceLoggingMetadata
0x1800017fc  mov     [r8+10h], rdx
0x180001800  mov     dword ptr [r8+0Ch], 2
0x180001808  movzx   eax, word ptr [rdx]
0x18000180b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001810  mov     [r8+18h], eax
0x180001814  lea     rax, _TraceLoggingMetadataEnd
0x18000181b  sub     eax, ecx
0x18000181d  mov     dword ptr [r8+1Ch], 1
0x180001825  mov     dword ptr [rsp+48h+arg_28], eax
0x180001829  mov     r8, r10; ActivityId
0x18000182c  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001830  mov     eax, [rsp+48h+arg_20]
0x180001834  mov     rcx, [r11+20h]; RegHandle
0x180001838  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000183c  call    cs:__imp_EventWriteTransfer
0x180001842  add     rsp, 48h
0x180001846  retn
```
