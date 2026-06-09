# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x1400010f4`
- end: `0x140001192`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `158`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x140001010`
- `0x140001198`
- `0x140001248`
- `0x1400012e4`
- `0x1400013c0`
- `0x140001878`
- `0x1400018f4`
- `0x14000d090`
- `0x14000e248`
- `0x140011a0c`
- `0x140017380`
- `0x14001a288`
- `0x14002c77c`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140001180`
- `ntoskrnl!EtwWriteTransfer` at `0x140001180`

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
  return EtwWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1400010f4  sub     rsp, 48h
0x1400010f8  movzx   eax, byte ptr [rdx]
0x1400010fb  mov     r11, rcx
0x1400010fe  shl     eax, 18h
0x140001101  mov     r10, r8
0x140001104  mov     r8, [rsp+48h+arg_28]
0x140001109  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x14000110d  movzx   eax, word ptr [rdx+1]
0x140001111  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001115  mov     rax, [rdx+3]
0x140001119  add     rdx, 0Bh
0x14000111d  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001122  mov     rax, [rcx+8]
0x140001126  mov     [r8], rax
0x140001129  mov     rax, [rcx+8]
0x14000112d  mov     [rsp+48h+UserData], r8; UserData
0x140001132  movzx   ecx, word ptr [rax]
0x140001135  mov     [r8+8], ecx
0x140001139  lea     rcx, _TraceLoggingMetadata
0x140001140  mov     [r8+10h], rdx
0x140001144  mov     dword ptr [r8+0Ch], 2
0x14000114c  movzx   eax, word ptr [rdx]
0x14000114f  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001154  mov     [r8+18h], eax
0x140001158  lea     rax, _TraceLoggingMetadataEnd
0x14000115f  sub     eax, ecx
0x140001161  mov     dword ptr [r8+1Ch], 1
0x140001169  mov     dword ptr [rsp+48h+arg_28], eax
0x14000116d  mov     r8, r10; ActivityId
0x140001170  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001174  mov     eax, [rsp+48h+arg_20]
0x140001178  mov     rcx, [r11+20h]; RegHandle
0x14000117c  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001180  call    cs:__imp_EtwWriteTransfer
0x140001187  nop     dword ptr [rax+rax+00h]
0x14000118c  add     rsp, 48h
0x140001190  retn
```
