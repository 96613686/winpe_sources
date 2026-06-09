# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001a8c`
- end: `0x140001b23`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x1400012e0`
- `0x1400013a4`
- `0x140001658`
- `0x140004ee0`
- `0x140009264`
- `0x14000b250`
- `0x140012cbc`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x140001b18`
- `ADVAPI32!EventWriteTransfer` at `0x140001b18`

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
0x140001a8c  sub     rsp, 48h
0x140001a90  movzx   eax, byte ptr [rdx]
0x140001a93  mov     r11, rcx
0x140001a96  shl     eax, 18h
0x140001a99  mov     r10, r8
0x140001a9c  mov     r8, [rsp+48h+arg_28]
0x140001aa1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001aa5  movzx   eax, word ptr [rdx+1]
0x140001aa9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001aad  mov     rax, [rdx+3]
0x140001ab1  add     rdx, 0Bh
0x140001ab5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001aba  mov     rax, [rcx+8]
0x140001abe  mov     [r8], rax
0x140001ac1  mov     rax, [rcx+8]
0x140001ac5  mov     [rsp+48h+UserData], r8; UserData
0x140001aca  movzx   ecx, word ptr [rax]
0x140001acd  mov     [r8+8], ecx
0x140001ad1  lea     rcx, _TraceLoggingMetadata
0x140001ad8  mov     [r8+10h], rdx
0x140001adc  mov     dword ptr [r8+0Ch], 2
0x140001ae4  movzx   eax, word ptr [rdx]
0x140001ae7  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001aec  mov     [r8+18h], eax
0x140001af0  lea     rax, _TraceLoggingMetadataEnd
0x140001af7  sub     eax, ecx
0x140001af9  mov     dword ptr [r8+1Ch], 1
0x140001b01  mov     dword ptr [rsp+48h+arg_28], eax
0x140001b05  mov     r8, r10; ActivityId
0x140001b08  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001b0c  mov     eax, [rsp+48h+arg_20]
0x140001b10  mov     rcx, [r11+20h]; RegHandle
0x140001b14  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001b18  call    cs:__imp_EventWriteTransfer
0x140001b1e  add     rsp, 48h
0x140001b22  retn
```
