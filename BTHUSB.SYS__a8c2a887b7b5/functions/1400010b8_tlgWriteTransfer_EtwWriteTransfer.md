# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x1400010b8`
- end: `0x140001156`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x14000115c`
- `0x140001304`
- `0x14000b14c`
- `0x14000ca2c`
- `0x14001accc`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140001144`
- `ntoskrnl!EtwWriteTransfer` at `0x140001144`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteTransfer_EtwWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int64 v6; // rax
  unsigned __int16 *v7; // rdx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v6;
  UserData->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData[1].Ptr = (unsigned __int64)v7;
  UserData->Reserved = 2;
  UserData[1].Size = *v7;
  UserData[1].Reserved = 1;
  return EtwWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1400010b8  sub     rsp, 48h
0x1400010bc  movzx   eax, byte ptr [rdx]
0x1400010bf  mov     r11, rcx
0x1400010c2  shl     eax, 18h
0x1400010c5  mov     r10, r8
0x1400010c8  mov     r8, [rsp+48h+arg_28]
0x1400010cd  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1400010d1  movzx   eax, word ptr [rdx+1]
0x1400010d5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1400010d9  mov     rax, [rdx+3]
0x1400010dd  add     rdx, 0Bh
0x1400010e1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1400010e6  mov     rax, [rcx+8]
0x1400010ea  mov     [r8], rax
0x1400010ed  mov     rax, [rcx+8]
0x1400010f1  mov     [rsp+48h+UserData], r8; UserData
0x1400010f6  movzx   ecx, word ptr [rax]
0x1400010f9  mov     [r8+8], ecx
0x1400010fd  lea     rcx, _TraceLoggingMetadata
0x140001104  mov     [r8+10h], rdx
0x140001108  mov     dword ptr [r8+0Ch], 2
0x140001110  movzx   eax, word ptr [rdx]
0x140001113  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001118  mov     [r8+18h], eax
0x14000111c  lea     rax, _TraceLoggingMetadataEnd
0x140001123  sub     eax, ecx
0x140001125  mov     dword ptr [r8+1Ch], 1
0x14000112d  mov     dword ptr [rsp+48h+arg_28], eax
0x140001131  mov     r8, r10; ActivityId
0x140001134  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001138  mov     eax, [rsp+48h+arg_20]
0x14000113c  mov     rcx, [r11+20h]; RegHandle
0x140001140  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001144  call    cs:__imp_EtwWriteTransfer
0x14000114b  nop     dword ptr [rax+rax+00h]
0x140001150  add     rsp, 48h
0x140001154  retn
```
