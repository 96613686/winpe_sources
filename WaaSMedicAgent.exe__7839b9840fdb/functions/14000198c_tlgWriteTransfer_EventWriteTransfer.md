# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x14000198c`
- end: `0x140001a23`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `22`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x1400012bc`
- `0x140001560`
- `0x140001a2c`
- `0x140001abc`
- `0x140001b4c`
- `0x140001e24`
- `0x140001ee8`
- `0x140001fe0`
- `0x1400078f4`
- `0x140008cac`
- `0x140008f2c`
- `0x1400090b0`
- `0x14000a120`
- `0x14000a314`
- `0x14000a4f0`
- `0x14000a8f0`
- `0x14000b304`
- `0x14000b470`
- `0x14000c6f0`
- `0x140010f14`
- `0x140011128`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001a18`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001a18`

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
0x14000198c  sub     rsp, 48h
0x140001990  movzx   eax, byte ptr [rdx]
0x140001993  mov     r11, rcx
0x140001996  shl     eax, 18h
0x140001999  mov     r10, r8
0x14000199c  mov     r8, [rsp+48h+arg_28]
0x1400019a1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1400019a5  movzx   eax, word ptr [rdx+1]
0x1400019a9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1400019ad  mov     rax, [rdx+3]
0x1400019b1  add     rdx, 0Bh
0x1400019b5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1400019ba  mov     rax, [rcx+8]
0x1400019be  mov     [r8], rax
0x1400019c1  mov     rax, [rcx+8]
0x1400019c5  mov     [rsp+48h+UserData], r8; UserData
0x1400019ca  movzx   ecx, word ptr [rax]
0x1400019cd  mov     [r8+8], ecx
0x1400019d1  lea     rcx, _TraceLoggingMetadata
0x1400019d8  mov     [r8+10h], rdx
0x1400019dc  mov     dword ptr [r8+0Ch], 2
0x1400019e4  movzx   eax, word ptr [rdx]
0x1400019e7  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1400019ec  mov     [r8+18h], eax
0x1400019f0  lea     rax, _TraceLoggingMetadataEnd
0x1400019f7  sub     eax, ecx
0x1400019f9  mov     dword ptr [r8+1Ch], 1
0x140001a01  mov     dword ptr [rsp+48h+arg_28], eax
0x140001a05  mov     r8, r10; ActivityId
0x140001a08  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001a0c  mov     eax, [rsp+48h+arg_20]
0x140001a10  mov     rcx, [r11+20h]; RegHandle
0x140001a14  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001a18  call    cs:__imp_EventWriteTransfer
0x140001a1e  add     rsp, 48h
0x140001a22  retn
```
