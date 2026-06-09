# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x1400010b4`
- end: `0x140001152`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `158`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x140001158`
- `0x140001300`
- `0x1400013ec`
- `0x1400014b0`
- `0x14000a660`
- `0x14000bb48`
- `0x14000c37c`
- `0x1400124a0`
- `0x140015a40`
- `0x14001b47c`
- `0x14001ffa4`
- `0x140025854`
- `0x140032c30`
- `0x140033970`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140001140`
- `ntoskrnl!EtwWriteTransfer` at `0x140001140`

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
0x1400010b4  sub     rsp, 48h
0x1400010b8  movzx   eax, byte ptr [rdx]
0x1400010bb  mov     r11, rcx
0x1400010be  shl     eax, 18h
0x1400010c1  mov     r10, r8
0x1400010c4  mov     r8, [rsp+48h+arg_28]
0x1400010c9  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1400010cd  movzx   eax, word ptr [rdx+1]
0x1400010d1  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1400010d5  mov     rax, [rdx+3]
0x1400010d9  add     rdx, 0Bh
0x1400010dd  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1400010e2  mov     rax, [rcx+8]
0x1400010e6  mov     [r8], rax
0x1400010e9  mov     rax, [rcx+8]
0x1400010ed  mov     [rsp+48h+UserData], r8; UserData
0x1400010f2  movzx   ecx, word ptr [rax]
0x1400010f5  mov     [r8+8], ecx
0x1400010f9  lea     rcx, _TraceLoggingMetadata
0x140001100  mov     [r8+10h], rdx
0x140001104  mov     dword ptr [r8+0Ch], 2
0x14000110c  movzx   eax, word ptr [rdx]
0x14000110f  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001114  mov     [r8+18h], eax
0x140001118  lea     rax, _TraceLoggingMetadataEnd
0x14000111f  sub     eax, ecx
0x140001121  mov     dword ptr [r8+1Ch], 1
0x140001129  mov     dword ptr [rsp+48h+arg_28], eax
0x14000112d  mov     r8, r10; ActivityId
0x140001130  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001134  mov     eax, [rsp+48h+arg_20]
0x140001138  mov     rcx, [r11+20h]; RegHandle
0x14000113c  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001140  call    cs:__imp_EtwWriteTransfer
0x140001147  nop     dword ptr [rax+rax+00h]
0x14000114c  add     rsp, 48h
0x140001150  retn
```
