# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001c94`
- end: `0x180001d2b`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180001308`
- `0x1800015e0`
- `0x1800018d8`
- `0x1800019e0`
- `0x180001d84`
- `0x180001e58`
- `0x180001f1c`
- `0x180001f90`
- `0x180002000`
- `0x18001079c`
- `0x180010a3c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001d20`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001d20`

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
0x180001c94  sub     rsp, 48h
0x180001c98  movzx   eax, byte ptr [rdx]
0x180001c9b  mov     r11, rcx
0x180001c9e  shl     eax, 18h
0x180001ca1  mov     r10, r8
0x180001ca4  mov     r8, [rsp+48h+arg_28]
0x180001ca9  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001cad  movzx   eax, word ptr [rdx+1]
0x180001cb1  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001cb5  mov     rax, [rdx+3]
0x180001cb9  add     rdx, 0Bh
0x180001cbd  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001cc2  mov     rax, [rcx+8]
0x180001cc6  mov     [r8], rax
0x180001cc9  mov     rax, [rcx+8]
0x180001ccd  mov     [rsp+48h+UserData], r8; UserData
0x180001cd2  movzx   ecx, word ptr [rax]
0x180001cd5  mov     [r8+8], ecx
0x180001cd9  lea     rcx, _TraceLoggingMetadata
0x180001ce0  mov     [r8+10h], rdx
0x180001ce4  mov     dword ptr [r8+0Ch], 2
0x180001cec  movzx   eax, word ptr [rdx]
0x180001cef  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001cf4  mov     [r8+18h], eax
0x180001cf8  lea     rax, _TraceLoggingMetadataEnd
0x180001cff  sub     eax, ecx
0x180001d01  mov     dword ptr [r8+1Ch], 1
0x180001d09  mov     dword ptr [rsp+48h+arg_28], eax
0x180001d0d  mov     r8, r10; ActivityId
0x180001d10  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001d14  mov     eax, [rsp+48h+arg_20]
0x180001d18  mov     rcx, [r11+20h]; RegHandle
0x180001d1c  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001d20  call    cs:__imp_EventWriteTransfer
0x180001d26  add     rsp, 48h
0x180001d2a  retn
```
