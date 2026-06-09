# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001bdc`
- end: `0x180001c73`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x180001098`
- `0x180001144`
- `0x18000120c`
- `0x1800014e4`
- `0x1800015a8`
- `0x18000185c`
- `0x180001c7c`
- `0x180001d58`
- `0x180001e50`
- `0x18000214c`
- `0x18000221c`
- `0x180009040`
- `0x18000d928`
- `0x18000f094`
- `0x18000f28c`
- `0x18000f4b0`
- `0x18000fbf0`
- `0x18000fee0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001c68`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001c68`

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
0x180001bdc  sub     rsp, 48h
0x180001be0  movzx   eax, byte ptr [rdx]
0x180001be3  mov     r11, rcx
0x180001be6  shl     eax, 18h
0x180001be9  mov     r10, r8
0x180001bec  mov     r8, [rsp+48h+arg_28]
0x180001bf1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001bf5  movzx   eax, word ptr [rdx+1]
0x180001bf9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001bfd  mov     rax, [rdx+3]
0x180001c01  add     rdx, 0Bh
0x180001c05  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001c0a  mov     rax, [rcx+8]
0x180001c0e  mov     [r8], rax
0x180001c11  mov     rax, [rcx+8]
0x180001c15  mov     [rsp+48h+UserData], r8; UserData
0x180001c1a  movzx   ecx, word ptr [rax]
0x180001c1d  mov     [r8+8], ecx
0x180001c21  lea     rcx, _TraceLoggingMetadata
0x180001c28  mov     [r8+10h], rdx
0x180001c2c  mov     dword ptr [r8+0Ch], 2
0x180001c34  movzx   eax, word ptr [rdx]
0x180001c37  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001c3c  mov     [r8+18h], eax
0x180001c40  lea     rax, _TraceLoggingMetadataEnd
0x180001c47  sub     eax, ecx
0x180001c49  mov     dword ptr [r8+1Ch], 1
0x180001c51  mov     dword ptr [rsp+48h+arg_28], eax
0x180001c55  mov     r8, r10; ActivityId
0x180001c58  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001c5c  mov     eax, [rsp+48h+arg_20]
0x180001c60  mov     rcx, [r11+20h]; RegHandle
0x180001c64  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001c68  call    cs:__imp_EventWriteTransfer
0x180001c6e  add     rsp, 48h
0x180001c72  retn
```
