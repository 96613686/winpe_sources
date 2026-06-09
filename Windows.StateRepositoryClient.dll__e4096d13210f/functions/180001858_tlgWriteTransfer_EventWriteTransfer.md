# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001858`
- end: `0x1800018ef`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x180001124`
- `0x1800013d8`
- `0x1800018f8`
- `0x1800019cc`
- `0x180001a70`
- `0x180001b04`
- `0x180001b98`
- `0x180001c10`
- `0x180001f24`
- `0x180001fb4`
- `0x1800020b0`
- `0x180018250`
- `0x180018c60`
- `0x180019250`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800018e4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800018e4`

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
0x180001858  sub     rsp, 48h
0x18000185c  movzx   eax, byte ptr [rdx]
0x18000185f  mov     r11, rcx
0x180001862  shl     eax, 18h
0x180001865  mov     r10, r8
0x180001868  mov     r8, [rsp+48h+arg_28]
0x18000186d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001871  movzx   eax, word ptr [rdx+1]
0x180001875  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001879  mov     rax, [rdx+3]
0x18000187d  add     rdx, 0Bh
0x180001881  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001886  mov     rax, [rcx+8]
0x18000188a  mov     [r8], rax
0x18000188d  mov     rax, [rcx+8]
0x180001891  mov     [rsp+48h+UserData], r8; UserData
0x180001896  movzx   ecx, word ptr [rax]
0x180001899  mov     [r8+8], ecx
0x18000189d  lea     rcx, _TraceLoggingMetadata
0x1800018a4  mov     [r8+10h], rdx
0x1800018a8  mov     dword ptr [r8+0Ch], 2
0x1800018b0  movzx   eax, word ptr [rdx]
0x1800018b3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800018b8  mov     [r8+18h], eax
0x1800018bc  lea     rax, _TraceLoggingMetadataEnd
0x1800018c3  sub     eax, ecx
0x1800018c5  mov     dword ptr [r8+1Ch], 1
0x1800018cd  mov     dword ptr [rsp+48h+arg_28], eax
0x1800018d1  mov     r8, r10; ActivityId
0x1800018d4  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800018d8  mov     eax, [rsp+48h+arg_20]
0x1800018dc  mov     rcx, [r11+20h]; RegHandle
0x1800018e0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800018e4  call    cs:__imp_EventWriteTransfer
0x1800018ea  add     rsp, 48h
0x1800018ee  retn
```
