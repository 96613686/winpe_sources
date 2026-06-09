# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001f08`
- end: `0x180001f9f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `57`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800012cc`
- `0x180001314`
- `0x180001628`
- `0x180001698`
- `0x180001724`
- `0x1800017e4`
- `0x180001a88`
- `0x180001fa8`
- `0x180002050`
- `0x180002110`
- `0x1800021d4`
- `0x1800024e4`
- `0x1800025bc`
- `0x1800026a4`
- `0x18000283c`
- `0x180002920`
- `0x180002a24`
- `0x180002a84`
- `0x180002af8`
- `0x180002c30`
- `0x180002d34`
- `0x180002d94`
- `0x180003090`
- `0x180003160`
- `0x180003224`
- `0x1800032e4`
- `0x1800033cc`
- `0x1800034c4`
- `0x180003624`
- `0x180003750`
- `0x1800038a0`
- `0x1800039b8`
- `0x180003ab0`
- `0x180003d9c`
- `0x180003e5c`
- `0x180003f30`
- `0x180003ff8`
- `0x1800040fc`
- `0x1800041f0`
- `0x18000429c`
- `0x180004390`
- `0x180004668`
- `0x18000473c`
- `0x180004800`
- `0x180004878`
- `0x18000496c`
- `0x180004a34`
- `0x180004af0`
- `0x180004dfc`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180001f94`
- `ADVAPI32!EventWriteTransfer` at `0x180001f94`

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
0x180001f08  sub     rsp, 48h
0x180001f0c  movzx   eax, byte ptr [rdx]
0x180001f0f  mov     r11, rcx
0x180001f12  shl     eax, 18h
0x180001f15  mov     r10, r8
0x180001f18  mov     r8, [rsp+48h+arg_28]
0x180001f1d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001f21  movzx   eax, word ptr [rdx+1]
0x180001f25  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001f29  mov     rax, [rdx+3]
0x180001f2d  add     rdx, 0Bh
0x180001f31  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001f36  mov     rax, [rcx+8]
0x180001f3a  mov     [r8], rax
0x180001f3d  mov     rax, [rcx+8]
0x180001f41  mov     [rsp+48h+UserData], r8; UserData
0x180001f46  movzx   ecx, word ptr [rax]
0x180001f49  mov     [r8+8], ecx
0x180001f4d  lea     rcx, _TraceLoggingMetadata
0x180001f54  mov     [r8+10h], rdx
0x180001f58  mov     dword ptr [r8+0Ch], 2
0x180001f60  movzx   eax, word ptr [rdx]
0x180001f63  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001f68  mov     [r8+18h], eax
0x180001f6c  lea     rax, _TraceLoggingMetadataEnd
0x180001f73  sub     eax, ecx
0x180001f75  mov     dword ptr [r8+1Ch], 1
0x180001f7d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001f81  mov     r8, r10; ActivityId
0x180001f84  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001f88  mov     eax, [rsp+48h+arg_20]
0x180001f8c  mov     rcx, [r11+20h]; RegHandle
0x180001f90  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001f94  call    cs:__imp_EventWriteTransfer
0x180001f9a  add     rsp, 48h
0x180001f9e  retn
```
