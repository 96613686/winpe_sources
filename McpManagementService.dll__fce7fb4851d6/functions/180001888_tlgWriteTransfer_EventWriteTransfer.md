# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001888`
- end: `0x18000191f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x180001158`
- `0x18000140c`
- `0x180001928`
- `0x180001a40`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001914`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001914`

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
0x180001888  sub     rsp, 48h
0x18000188c  movzx   eax, byte ptr [rdx]
0x18000188f  mov     r11, rcx
0x180001892  shl     eax, 18h
0x180001895  mov     r10, r8
0x180001898  mov     r8, [rsp+48h+arg_28]
0x18000189d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800018a1  movzx   eax, word ptr [rdx+1]
0x1800018a5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800018a9  mov     rax, [rdx+3]
0x1800018ad  add     rdx, 0Bh
0x1800018b1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800018b6  mov     rax, [rcx+8]
0x1800018ba  mov     [r8], rax
0x1800018bd  mov     rax, [rcx+8]
0x1800018c1  mov     [rsp+48h+UserData], r8; UserData
0x1800018c6  movzx   ecx, word ptr [rax]
0x1800018c9  mov     [r8+8], ecx
0x1800018cd  lea     rcx, _TraceLoggingMetadata
0x1800018d4  mov     [r8+10h], rdx
0x1800018d8  mov     dword ptr [r8+0Ch], 2
0x1800018e0  movzx   eax, word ptr [rdx]
0x1800018e3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800018e8  mov     [r8+18h], eax
0x1800018ec  lea     rax, _TraceLoggingMetadataEnd
0x1800018f3  sub     eax, ecx
0x1800018f5  mov     dword ptr [r8+1Ch], 1
0x1800018fd  mov     dword ptr [rsp+48h+arg_28], eax
0x180001901  mov     r8, r10; ActivityId
0x180001904  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001908  mov     eax, [rsp+48h+arg_20]
0x18000190c  mov     rcx, [r11+20h]; RegHandle
0x180001910  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001914  call    cs:__imp_EventWriteTransfer
0x18000191a  add     rsp, 48h
0x18000191e  retn
```
