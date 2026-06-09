# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001970`
- end: `0x180001a0e`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `21`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800012bc`
- `0x18000134c`
- `0x1800015f0`
- `0x1800058b8`
- `0x180008648`
- `0x18000877c`
- `0x180010c5c`
- `0x18001bb20`
- `0x18001bc8c`
- `0x18001bdc0`
- `0x18001bfb4`
- `0x18001c0e8`
- `0x18001c21c`
- `0x18001c350`
- `0x18001c50c`
- `0x18001c640`
- `0x18001c774`
- `0x18001c8a8`
- `0x18001c9dc`
- `0x180022f5c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800019fc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800019fc`

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
0x180001970  sub     rsp, 48h
0x180001974  movzx   eax, byte ptr [rdx]
0x180001977  mov     r11, rcx
0x18000197a  shl     eax, 18h
0x18000197d  mov     r10, r8
0x180001980  mov     r8, [rsp+48h+arg_28]
0x180001985  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001989  movzx   eax, word ptr [rdx+1]
0x18000198d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001991  mov     rax, [rdx+3]
0x180001995  add     rdx, 0Bh
0x180001999  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000199e  mov     rax, [rcx+8]
0x1800019a2  mov     [r8], rax
0x1800019a5  mov     rax, [rcx+8]
0x1800019a9  mov     [rsp+48h+UserData], r8; UserData
0x1800019ae  movzx   ecx, word ptr [rax]
0x1800019b1  mov     [r8+8], ecx
0x1800019b5  lea     rcx, _TraceLoggingMetadata
0x1800019bc  mov     [r8+10h], rdx
0x1800019c0  mov     dword ptr [r8+0Ch], 2
0x1800019c8  movzx   eax, word ptr [rdx]
0x1800019cb  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800019d0  mov     [r8+18h], eax
0x1800019d4  lea     rax, _TraceLoggingMetadataEnd
0x1800019db  sub     eax, ecx
0x1800019dd  mov     dword ptr [r8+1Ch], 1
0x1800019e5  mov     dword ptr [rsp+48h+arg_28], eax
0x1800019e9  mov     r8, r10; ActivityId
0x1800019ec  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800019f0  mov     eax, [rsp+48h+arg_20]
0x1800019f4  mov     rcx, [r11+20h]; RegHandle
0x1800019f8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800019fc  call    cs:__imp_EventWriteTransfer
0x180001a03  nop     dword ptr [rax+rax+00h]
0x180001a08  add     rsp, 48h
0x180001a0c  retn
```
