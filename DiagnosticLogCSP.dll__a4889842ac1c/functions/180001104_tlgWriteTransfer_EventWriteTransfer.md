# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001104`
- end: `0x18000119b`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD)`
- caller_count: `31`
- callee_count: `0`
- tags: ``

## callers

- `0x18000108c`
- `0x1800011a4`
- `0x180001250`
- `0x180001318`
- `0x180009260`
- `0x18000a720`
- `0x18000a820`
- `0x18000b570`
- `0x18000b620`
- `0x18000b9d0`
- `0x18000cb9c`
- `0x18000d9e0`
- `0x18000e4cc`
- `0x18000e7e8`
- `0x18000f0c0`
- `0x18000f6fc`
- `0x18001047c`
- `0x180011cd4`
- `0x180012890`
- `0x180012a24`
- `0x180012aec`
- `0x180012ddc`
- `0x180013294`
- `0x1800133bc`
- `0x180013460`
- `0x180013500`
- `0x180014004`
- `0x180018020`
- `0x1800196c0`
- `0x180019f58`
- `0x180020204`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001190`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001190`

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
0x180001104  sub     rsp, 48h
0x180001108  movzx   eax, byte ptr [rdx]
0x18000110b  mov     r11, rcx
0x18000110e  shl     eax, 18h
0x180001111  mov     r10, r8
0x180001114  mov     r8, [rsp+48h+arg_28]
0x180001119  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000111d  movzx   eax, word ptr [rdx+1]
0x180001121  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001125  mov     rax, [rdx+3]
0x180001129  add     rdx, 0Bh
0x18000112d  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001132  mov     rax, [rcx+8]
0x180001136  mov     [r8], rax
0x180001139  mov     rax, [rcx+8]
0x18000113d  mov     [rsp+48h+UserData], r8; UserData
0x180001142  movzx   ecx, word ptr [rax]
0x180001145  mov     [r8+8], ecx
0x180001149  lea     rcx, _TraceLoggingMetadata
0x180001150  mov     [r8+10h], rdx
0x180001154  mov     dword ptr [r8+0Ch], 2
0x18000115c  movzx   eax, word ptr [rdx]
0x18000115f  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001164  mov     [r8+18h], eax
0x180001168  lea     rax, _TraceLoggingMetadataEnd
0x18000116f  sub     eax, ecx
0x180001171  mov     dword ptr [r8+1Ch], 1
0x180001179  mov     dword ptr [rsp+48h+arg_28], eax
0x18000117d  mov     r8, r10; ActivityId
0x180001180  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001184  mov     eax, [rsp+48h+arg_20]
0x180001188  mov     rcx, [r11+20h]; RegHandle
0x18000118c  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001190  call    cs:__imp_EventWriteTransfer
0x180001196  add     rsp, 48h
0x18000119a  retn
```
