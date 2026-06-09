# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001038`
- end: `0x1400010d6`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `26`
- callee_count: `0`
- tags: ``

## callers

- `0x1400010dc`
- `0x1400011a8`
- `0x140001288`
- `0x14000131c`
- `0x140001394`
- `0x140001484`
- `0x140001558`
- `0x14000162c`
- `0x140001694`
- `0x140001a78`
- `0x140001b6c`
- `0x140001c3c`
- `0x140002488`
- `0x1400028e4`
- `0x140002978`
- `0x1400029d8`
- `0x140002a50`
- `0x140002ae4`
- `0x140002b78`
- `0x140002bf0`
- `0x140002c84`
- `0x140002d18`
- `0x140002dac`
- `0x140058b28`
- `0x1400777d0`
- `0x1400dd68c`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400010c4`
- `ntoskrnl!EtwWriteTransfer` at `0x1400010c4`

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
0x140001038  sub     rsp, 48h
0x14000103c  movzx   eax, byte ptr [rdx]
0x14000103f  mov     r11, rcx
0x140001042  shl     eax, 18h
0x140001045  mov     r10, r8
0x140001048  mov     r8, [rsp+48h+arg_28]
0x14000104d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001051  movzx   eax, word ptr [rdx+1]
0x140001055  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001059  mov     rax, [rdx+3]
0x14000105d  add     rdx, 0Bh
0x140001061  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001066  mov     rax, [rcx+8]
0x14000106a  mov     [r8], rax
0x14000106d  mov     rax, [rcx+8]
0x140001071  mov     [rsp+48h+UserData], r8; UserData
0x140001076  movzx   ecx, word ptr [rax]
0x140001079  mov     [r8+8], ecx
0x14000107d  lea     rcx, _TraceLoggingMetadata
0x140001084  mov     [r8+10h], rdx
0x140001088  mov     dword ptr [r8+0Ch], 2
0x140001090  movzx   eax, word ptr [rdx]
0x140001093  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001098  mov     [r8+18h], eax
0x14000109c  lea     rax, _TraceLoggingMetadataEnd
0x1400010a3  sub     eax, ecx
0x1400010a5  mov     dword ptr [r8+1Ch], 1
0x1400010ad  mov     dword ptr [rsp+48h+arg_28], eax
0x1400010b1  mov     r8, r10; ActivityId
0x1400010b4  mov     eax, dword ptr [rsp+48h+arg_28]
0x1400010b8  mov     eax, [rsp+48h+arg_20]
0x1400010bc  mov     rcx, [r11+20h]; RegHandle
0x1400010c0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400010c4  call    cs:__imp_EtwWriteTransfer
0x1400010cb  nop     dword ptr [rax+rax+00h]
0x1400010d0  add     rsp, 48h
0x1400010d4  retn
```
