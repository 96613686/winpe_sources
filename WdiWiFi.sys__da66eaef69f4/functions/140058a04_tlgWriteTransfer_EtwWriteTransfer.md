# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140058a04`
- end: `0x140058aa2`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `158`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `21`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x1400010f8`
- `0x1400011c8`
- `0x140001248`
- `0x140001308`
- `0x1400013e8`
- `0x1400014b8`
- `0x14000158c`
- `0x140001650`
- `0x1400016f8`
- `0x140001758`
- `0x1400017c0`
- `0x14000187c`
- `0x140001970`
- `0x140001a40`
- `0x140001ad4`
- `0x140001b4c`
- `0x140001be0`
- `0x14009d734`
- `0x1400ae990`
- `0x1400d9fc4`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140058a90`
- `ntoskrnl!EtwWriteTransfer` at `0x140058a90`

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
0x140058a04  sub     rsp, 48h
0x140058a08  movzx   eax, byte ptr [rdx]
0x140058a0b  mov     r11, rcx
0x140058a0e  shl     eax, 18h
0x140058a11  mov     r10, r8
0x140058a14  mov     r8, [rsp+48h+arg_28]
0x140058a19  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140058a1d  movzx   eax, word ptr [rdx+1]
0x140058a21  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140058a25  mov     rax, [rdx+3]
0x140058a29  add     rdx, 0Bh
0x140058a2d  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140058a32  mov     rax, [rcx+8]
0x140058a36  mov     [r8], rax
0x140058a39  mov     rax, [rcx+8]
0x140058a3d  mov     [rsp+48h+UserData], r8; UserData
0x140058a42  movzx   ecx, word ptr [rax]
0x140058a45  mov     [r8+8], ecx
0x140058a49  lea     rcx, _TraceLoggingMetadata
0x140058a50  mov     [r8+10h], rdx
0x140058a54  mov     dword ptr [r8+0Ch], 2
0x140058a5c  movzx   eax, word ptr [rdx]
0x140058a5f  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140058a64  mov     [r8+18h], eax
0x140058a68  lea     rax, _TraceLoggingMetadataEnd
0x140058a6f  sub     eax, ecx
0x140058a71  mov     dword ptr [r8+1Ch], 1
0x140058a79  mov     dword ptr [rsp+48h+arg_28], eax
0x140058a7d  mov     r8, r10; ActivityId
0x140058a80  mov     eax, dword ptr [rsp+48h+arg_28]
0x140058a84  mov     eax, [rsp+48h+arg_20]
0x140058a88  mov     rcx, [r11+20h]; RegHandle
0x140058a8c  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140058a90  call    cs:__imp_EtwWriteTransfer
0x140058a97  nop     dword ptr [rax+rax+00h]
0x140058a9c  add     rsp, 48h
0x140058aa0  retn
```
