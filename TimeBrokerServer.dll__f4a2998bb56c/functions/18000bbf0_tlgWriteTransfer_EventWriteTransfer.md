# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000bbf0`
- end: `0x18000bc87`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x18000106c`
- `0x1800010e8`
- `0x1800011b0`
- `0x1800012f8`
- `0x180001500`
- `0x180001654`
- `0x180001c14`
- `0x18000ba98`
- `0x18000bba0`
- `0x180010350`
- `0x180013ca0`
- `0x180015178`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000bc7c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000bc7c`

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
0x18000bbf0  sub     rsp, 48h
0x18000bbf4  movzx   eax, byte ptr [rdx]
0x18000bbf7  mov     r11, rcx
0x18000bbfa  shl     eax, 18h
0x18000bbfd  mov     r10, r8
0x18000bc00  mov     r8, [rsp+48h+arg_28]
0x18000bc05  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000bc09  movzx   eax, word ptr [rdx+1]
0x18000bc0d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000bc11  mov     rax, [rdx+3]
0x18000bc15  add     rdx, 0Bh
0x18000bc19  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000bc1e  mov     rax, [rcx+8]
0x18000bc22  mov     [r8], rax
0x18000bc25  mov     rax, [rcx+8]
0x18000bc29  mov     [rsp+48h+UserData], r8; UserData
0x18000bc2e  movzx   ecx, word ptr [rax]
0x18000bc31  mov     [r8+8], ecx
0x18000bc35  lea     rcx, _TraceLoggingMetadata
0x18000bc3c  mov     [r8+10h], rdx
0x18000bc40  mov     dword ptr [r8+0Ch], 2
0x18000bc48  movzx   eax, word ptr [rdx]
0x18000bc4b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000bc50  mov     [r8+18h], eax
0x18000bc54  lea     rax, _TraceLoggingMetadataEnd
0x18000bc5b  sub     eax, ecx
0x18000bc5d  mov     dword ptr [r8+1Ch], 1
0x18000bc65  mov     dword ptr [rsp+48h+arg_28], eax
0x18000bc69  mov     r8, r10; ActivityId
0x18000bc6c  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000bc70  mov     eax, [rsp+48h+arg_20]
0x18000bc74  mov     rcx, [r11+20h]; RegHandle
0x18000bc78  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000bc7c  call    cs:__imp_EventWriteTransfer
0x18000bc82  add     rsp, 48h
0x18000bc86  retn
```
