# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001058`
- end: `0x1400010ef`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x140001010`
- `0x1400010f8`
- `0x140001158`
- `0x1400011c4`
- `0x140001264`
- `0x1400012bc`
- `0x140001544`
- `0x1400017dc`
- `0x140001ab8`
- `0x140001b28`
- `0x140001bb4`
- `0x140002028`
- `0x1400020e8`
- `0x140002190`
- `0x140002274`
- `0x140002330`
- `0x1400023d8`
- `0x1400024cc`
- `0x140009f70`
- `0x14000eee0`
- `0x14000f604`
- `0x140027ed4`
- `0x140027f90`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400010e4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400010e4`

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
0x140001058  sub     rsp, 48h
0x14000105c  movzx   eax, byte ptr [rdx]
0x14000105f  mov     r11, rcx
0x140001062  shl     eax, 18h
0x140001065  mov     r10, r8
0x140001068  mov     r8, [rsp+48h+arg_28]
0x14000106d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001071  movzx   eax, word ptr [rdx+1]
0x140001075  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001079  mov     rax, [rdx+3]
0x14000107d  add     rdx, 0Bh
0x140001081  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001086  mov     rax, [rcx+8]
0x14000108a  mov     [r8], rax
0x14000108d  mov     rax, [rcx+8]
0x140001091  mov     [rsp+48h+UserData], r8; UserData
0x140001096  movzx   ecx, word ptr [rax]
0x140001099  mov     [r8+8], ecx
0x14000109d  lea     rcx, _TraceLoggingMetadata
0x1400010a4  mov     [r8+10h], rdx
0x1400010a8  mov     dword ptr [r8+0Ch], 2
0x1400010b0  movzx   eax, word ptr [rdx]
0x1400010b3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1400010b8  mov     [r8+18h], eax
0x1400010bc  lea     rax, _TraceLoggingMetadataEnd
0x1400010c3  sub     eax, ecx
0x1400010c5  mov     dword ptr [r8+1Ch], 1
0x1400010cd  mov     dword ptr [rsp+48h+arg_28], eax
0x1400010d1  mov     r8, r10; ActivityId
0x1400010d4  mov     eax, dword ptr [rsp+48h+arg_28]
0x1400010d8  mov     eax, [rsp+48h+arg_20]
0x1400010dc  mov     rcx, [r11+20h]; RegHandle
0x1400010e0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400010e4  call    cs:__imp_EventWriteTransfer
0x1400010ea  add     rsp, 48h
0x1400010ee  retn
```
