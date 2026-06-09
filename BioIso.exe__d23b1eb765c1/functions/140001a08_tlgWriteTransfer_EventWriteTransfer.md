# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001a08`
- end: `0x140001aa6`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x14000131c`
- `0x14000146c`
- `0x140001764`
- `0x140002094`
- `0x1400020dc`
- `0x1400022f0`
- `0x1400023c4`
- `0x140002488`
- `0x140002514`
- `0x1400025ec`
- `0x140040e30`
- `0x140041f50`
- `0x140042eb0`
- `0x14005dd04`
- `0x140061ecc`
- `0x1400620a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001a94`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001a94`

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
0x140001a08  sub     rsp, 48h
0x140001a0c  movzx   eax, byte ptr [rdx]
0x140001a0f  mov     r11, rcx
0x140001a12  shl     eax, 18h
0x140001a15  mov     r10, r8
0x140001a18  mov     r8, [rsp+48h+arg_28]
0x140001a1d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001a21  movzx   eax, word ptr [rdx+1]
0x140001a25  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001a29  mov     rax, [rdx+3]
0x140001a2d  add     rdx, 0Bh
0x140001a31  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001a36  mov     rax, [rcx+8]
0x140001a3a  mov     [r8], rax
0x140001a3d  mov     rax, [rcx+8]
0x140001a41  mov     [rsp+48h+UserData], r8; UserData
0x140001a46  movzx   ecx, word ptr [rax]
0x140001a49  mov     [r8+8], ecx
0x140001a4d  lea     rcx, _TraceLoggingMetadata
0x140001a54  mov     [r8+10h], rdx
0x140001a58  mov     dword ptr [r8+0Ch], 2
0x140001a60  movzx   eax, word ptr [rdx]
0x140001a63  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001a68  mov     [r8+18h], eax
0x140001a6c  lea     rax, _TraceLoggingMetadataEnd
0x140001a73  sub     eax, ecx
0x140001a75  mov     dword ptr [r8+1Ch], 1
0x140001a7d  mov     dword ptr [rsp+48h+arg_28], eax
0x140001a81  mov     r8, r10; ActivityId
0x140001a84  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001a88  mov     eax, [rsp+48h+arg_20]
0x140001a8c  mov     rcx, [r11+20h]; RegHandle
0x140001a90  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001a94  call    cs:__imp_EventWriteTransfer
0x140001a9b  nop     dword ptr [rax+rax+00h]
0x140001aa0  add     rsp, 48h
0x140001aa4  retn
```
