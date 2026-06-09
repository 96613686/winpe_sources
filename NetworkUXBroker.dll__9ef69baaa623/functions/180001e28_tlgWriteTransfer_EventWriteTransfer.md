# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001e28`
- end: `0x180001ebf`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800012cc`
- `0x18000135c`
- `0x180001444`
- `0x180001708`
- `0x1800019ac`
- `0x1800254c0`
- `0x18003104c`
- `0x1800313dc`
- `0x180031680`
- `0x180033538`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001eb4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001eb4`

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
0x180001e28  sub     rsp, 48h
0x180001e2c  movzx   eax, byte ptr [rdx]
0x180001e2f  mov     r11, rcx
0x180001e32  shl     eax, 18h
0x180001e35  mov     r10, r8
0x180001e38  mov     r8, [rsp+48h+arg_28]
0x180001e3d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001e41  movzx   eax, word ptr [rdx+1]
0x180001e45  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001e49  mov     rax, [rdx+3]
0x180001e4d  add     rdx, 0Bh
0x180001e51  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001e56  mov     rax, [rcx+8]
0x180001e5a  mov     [r8], rax
0x180001e5d  mov     rax, [rcx+8]
0x180001e61  mov     [rsp+48h+UserData], r8; UserData
0x180001e66  movzx   ecx, word ptr [rax]
0x180001e69  mov     [r8+8], ecx
0x180001e6d  lea     rcx, _TraceLoggingMetadata
0x180001e74  mov     [r8+10h], rdx
0x180001e78  mov     dword ptr [r8+0Ch], 2
0x180001e80  movzx   eax, word ptr [rdx]
0x180001e83  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001e88  mov     [r8+18h], eax
0x180001e8c  lea     rax, _TraceLoggingMetadataEnd
0x180001e93  sub     eax, ecx
0x180001e95  mov     dword ptr [r8+1Ch], 1
0x180001e9d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001ea1  mov     r8, r10; ActivityId
0x180001ea4  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001ea8  mov     eax, [rsp+48h+arg_20]
0x180001eac  mov     rcx, [r11+20h]; RegHandle
0x180001eb0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001eb4  call    cs:__imp_EventWriteTransfer
0x180001eba  add     rsp, 48h
0x180001ebe  retn
```
