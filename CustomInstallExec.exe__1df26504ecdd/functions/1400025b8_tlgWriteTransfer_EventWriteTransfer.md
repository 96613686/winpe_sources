# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1400025b8`
- end: `0x14000264f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x140001010`
- `0x1400012cc`
- `0x1400013e8`
- `0x1400014b4`
- `0x1400017e8`
- `0x140001b5c`
- `0x140001bcc`
- `0x140001c5c`
- `0x140001d50`
- `0x140001e94`
- `0x140002138`
- `0x14000811c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002644`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002644`

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
0x1400025b8  sub     rsp, 48h
0x1400025bc  movzx   eax, byte ptr [rdx]
0x1400025bf  mov     r11, rcx
0x1400025c2  shl     eax, 18h
0x1400025c5  mov     r10, r8
0x1400025c8  mov     r8, [rsp+48h+arg_28]
0x1400025cd  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1400025d1  movzx   eax, word ptr [rdx+1]
0x1400025d5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1400025d9  mov     rax, [rdx+3]
0x1400025dd  add     rdx, 0Bh
0x1400025e1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1400025e6  mov     rax, [rcx+8]
0x1400025ea  mov     [r8], rax
0x1400025ed  mov     rax, [rcx+8]
0x1400025f1  mov     [rsp+48h+UserData], r8; UserData
0x1400025f6  movzx   ecx, word ptr [rax]
0x1400025f9  mov     [r8+8], ecx
0x1400025fd  lea     rcx, _TraceLoggingMetadata
0x140002604  mov     [r8+10h], rdx
0x140002608  mov     dword ptr [r8+0Ch], 2
0x140002610  movzx   eax, word ptr [rdx]
0x140002613  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140002618  mov     [r8+18h], eax
0x14000261c  lea     rax, _TraceLoggingMetadataEnd
0x140002623  sub     eax, ecx
0x140002625  mov     dword ptr [r8+1Ch], 1
0x14000262d  mov     dword ptr [rsp+48h+arg_28], eax
0x140002631  mov     r8, r10; ActivityId
0x140002634  mov     eax, dword ptr [rsp+48h+arg_28]
0x140002638  mov     eax, [rsp+48h+arg_20]
0x14000263c  mov     rcx, [r11+20h]; RegHandle
0x140002640  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140002644  call    cs:__imp_EventWriteTransfer
0x14000264a  add     rsp, 48h
0x14000264e  retn
```
