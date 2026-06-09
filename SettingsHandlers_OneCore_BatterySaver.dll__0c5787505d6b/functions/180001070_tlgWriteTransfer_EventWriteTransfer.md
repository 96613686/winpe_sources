# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001070`
- end: `0x180001107`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x180001110`
- `0x180001188`
- `0x18000143c`
- `0x1800014ac`
- `0x18000153c`
- `0x1800017e0`
- `0x180001c68`
- `0x180001f40`
- `0x180002014`
- `0x180017bfc`
- `0x18003ed70`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800010fc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800010fc`

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
0x180001070  sub     rsp, 48h
0x180001074  movzx   eax, byte ptr [rdx]
0x180001077  mov     r11, rcx
0x18000107a  shl     eax, 18h
0x18000107d  mov     r10, r8
0x180001080  mov     r8, [rsp+48h+arg_28]
0x180001085  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001089  movzx   eax, word ptr [rdx+1]
0x18000108d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001091  mov     rax, [rdx+3]
0x180001095  add     rdx, 0Bh
0x180001099  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000109e  mov     rax, [rcx+8]
0x1800010a2  mov     [r8], rax
0x1800010a5  mov     rax, [rcx+8]
0x1800010a9  mov     [rsp+48h+UserData], r8; UserData
0x1800010ae  movzx   ecx, word ptr [rax]
0x1800010b1  mov     [r8+8], ecx
0x1800010b5  lea     rcx, _TraceLoggingMetadata
0x1800010bc  mov     [r8+10h], rdx
0x1800010c0  mov     dword ptr [r8+0Ch], 2
0x1800010c8  movzx   eax, word ptr [rdx]
0x1800010cb  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800010d0  mov     [r8+18h], eax
0x1800010d4  lea     rax, _TraceLoggingMetadataEnd
0x1800010db  sub     eax, ecx
0x1800010dd  mov     dword ptr [r8+1Ch], 1
0x1800010e5  mov     dword ptr [rsp+48h+arg_28], eax
0x1800010e9  mov     r8, r10; ActivityId
0x1800010ec  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800010f0  mov     eax, [rsp+48h+arg_20]
0x1800010f4  mov     rcx, [r11+20h]; RegHandle
0x1800010f8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800010fc  call    cs:__imp_EventWriteTransfer
0x180001102  add     rsp, 48h
0x180001106  retn
```
