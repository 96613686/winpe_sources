# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x14000110c`
- end: `0x1400011aa`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `158`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `34`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x1400011b0`
- `0x140001250`
- `0x14000132c`
- `0x1400013ac`
- `0x140001488`
- `0x140001534`
- `0x1400015ec`
- `0x140001708`
- `0x1400017a4`
- `0x1400017f4`
- `0x140001890`
- `0x14000192c`
- `0x1400019d4`
- `0x140001a70`
- `0x140001bd8`
- `0x140001c88`
- `0x140001d34`
- `0x140001e10`
- `0x140001e90`
- `0x140001f2c`
- `0x140002008`
- `0x1400020e4`
- `0x140002190`
- `0x140002248`
- `0x140014788`
- `0x14001a228`
- `0x1400318b8`
- `0x140031b00`
- `0x140042c18`
- `0x14007dc1c`
- `0x140083540`
- `0x140083af4`
- `0x140085ae8`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140001198`
- `ntoskrnl!EtwWriteTransfer` at `0x140001198`

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
0x14000110c  sub     rsp, 48h
0x140001110  movzx   eax, byte ptr [rdx]
0x140001113  mov     r11, rcx
0x140001116  shl     eax, 18h
0x140001119  mov     r10, r8
0x14000111c  mov     r8, [rsp+48h+arg_28]
0x140001121  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001125  movzx   eax, word ptr [rdx+1]
0x140001129  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x14000112d  mov     rax, [rdx+3]
0x140001131  add     rdx, 0Bh
0x140001135  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x14000113a  mov     rax, [rcx+8]
0x14000113e  mov     [r8], rax
0x140001141  mov     rax, [rcx+8]
0x140001145  mov     [rsp+48h+UserData], r8; UserData
0x14000114a  movzx   ecx, word ptr [rax]
0x14000114d  mov     [r8+8], ecx
0x140001151  lea     rcx, _TraceLoggingMetadata
0x140001158  mov     [r8+10h], rdx
0x14000115c  mov     dword ptr [r8+0Ch], 2
0x140001164  movzx   eax, word ptr [rdx]
0x140001167  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x14000116c  mov     [r8+18h], eax
0x140001170  lea     rax, _TraceLoggingMetadataEnd
0x140001177  sub     eax, ecx
0x140001179  mov     dword ptr [r8+1Ch], 1
0x140001181  mov     dword ptr [rsp+48h+arg_28], eax
0x140001185  mov     r8, r10; ActivityId
0x140001188  mov     eax, dword ptr [rsp+48h+arg_28]
0x14000118c  mov     eax, [rsp+48h+arg_20]
0x140001190  mov     rcx, [r11+20h]; RegHandle
0x140001194  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001198  call    cs:__imp_EtwWriteTransfer
0x14000119f  nop     dword ptr [rax+rax+00h]
0x1400011a4  add     rsp, 48h
0x1400011a8  retn
```
