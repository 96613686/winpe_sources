# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800014e8`
- end: `0x18000157f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `36`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x180001314`
- `0x180001588`
- `0x180001614`
- `0x180001674`
- `0x180001708`
- `0x1800017a0`
- `0x18000183c`
- `0x1800018d8`
- `0x180001984`
- `0x180001a30`
- `0x180001aa4`
- `0x180001bbc`
- `0x180001e70`
- `0x180001efc`
- `0x180001fdc`
- `0x18000209c`
- `0x180002340`
- `0x1800023dc`
- `0x180002474`
- `0x1800024e4`
- `0x180002620`
- `0x1800026ec`
- `0x1800027b8`
- `0x1800028e0`
- `0x18000295c`
- `0x180002a20`
- `0x180019350`
- `0x18002046c`
- `0x180021570`
- `0x1800368b8`
- `0x180036aa8`
- `0x18003fc34`
- `0x1800453ac`
- `0x1800455c8`
- `0x180047ae0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001574`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001574`

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
0x1800014e8  sub     rsp, 48h
0x1800014ec  movzx   eax, byte ptr [rdx]
0x1800014ef  mov     r11, rcx
0x1800014f2  shl     eax, 18h
0x1800014f5  mov     r10, r8
0x1800014f8  mov     r8, [rsp+48h+arg_28]
0x1800014fd  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001501  movzx   eax, word ptr [rdx+1]
0x180001505  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001509  mov     rax, [rdx+3]
0x18000150d  add     rdx, 0Bh
0x180001511  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001516  mov     rax, [rcx+8]
0x18000151a  mov     [r8], rax
0x18000151d  mov     rax, [rcx+8]
0x180001521  mov     [rsp+48h+UserData], r8; UserData
0x180001526  movzx   ecx, word ptr [rax]
0x180001529  mov     [r8+8], ecx
0x18000152d  lea     rcx, _TraceLoggingMetadata
0x180001534  mov     [r8+10h], rdx
0x180001538  mov     dword ptr [r8+0Ch], 2
0x180001540  movzx   eax, word ptr [rdx]
0x180001543  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001548  mov     [r8+18h], eax
0x18000154c  lea     rax, _TraceLoggingMetadataEnd
0x180001553  sub     eax, ecx
0x180001555  mov     dword ptr [r8+1Ch], 1
0x18000155d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001561  mov     r8, r10; ActivityId
0x180001564  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001568  mov     eax, [rsp+48h+arg_20]
0x18000156c  mov     rcx, [r11+20h]; RegHandle
0x180001570  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001574  call    cs:__imp_EventWriteTransfer
0x18000157a  add     rsp, 48h
0x18000157e  retn
```
