# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001578`
- end: `0x18000160f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x180001184`
- `0x1800012c4`
- `0x180001618`
- `0x18000178c`
- `0x18000192c`
- `0x180001a2c`
- `0x180001b5c`
- `0x180001c60`
- `0x180001df8`
- `0x1800020e4`
- `0x180002284`
- `0x180002510`
- `0x180002654`
- `0x1800029cc`
- `0x180002b14`
- `0x180002c8c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001604`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001604`

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
0x180001578  sub     rsp, 48h
0x18000157c  movzx   eax, byte ptr [rdx]
0x18000157f  mov     r11, rcx
0x180001582  shl     eax, 18h
0x180001585  mov     r10, r8
0x180001588  mov     r8, [rsp+48h+arg_28]
0x18000158d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001591  movzx   eax, word ptr [rdx+1]
0x180001595  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001599  mov     rax, [rdx+3]
0x18000159d  add     rdx, 0Bh
0x1800015a1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800015a6  mov     rax, [rcx+8]
0x1800015aa  mov     [r8], rax
0x1800015ad  mov     rax, [rcx+8]
0x1800015b1  mov     [rsp+48h+UserData], r8; UserData
0x1800015b6  movzx   ecx, word ptr [rax]
0x1800015b9  mov     [r8+8], ecx
0x1800015bd  lea     rcx, _TraceLoggingMetadata
0x1800015c4  mov     [r8+10h], rdx
0x1800015c8  mov     dword ptr [r8+0Ch], 2
0x1800015d0  movzx   eax, word ptr [rdx]
0x1800015d3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800015d8  mov     [r8+18h], eax
0x1800015dc  lea     rax, _TraceLoggingMetadataEnd
0x1800015e3  sub     eax, ecx
0x1800015e5  mov     dword ptr [r8+1Ch], 1
0x1800015ed  mov     dword ptr [rsp+48h+arg_28], eax
0x1800015f1  mov     r8, r10; ActivityId
0x1800015f4  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800015f8  mov     eax, [rsp+48h+arg_20]
0x1800015fc  mov     rcx, [r11+20h]; RegHandle
0x180001600  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001604  call    cs:__imp_EventWriteTransfer
0x18000160a  add     rsp, 48h
0x18000160e  retn
```
