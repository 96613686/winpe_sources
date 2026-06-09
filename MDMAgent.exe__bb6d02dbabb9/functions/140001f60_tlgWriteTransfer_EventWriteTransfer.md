# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001f60`
- end: `0x140001ffe`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x140001010`
- `0x140001330`
- `0x140001378`
- `0x14000162c`
- `0x14000169c`
- `0x14000172c`
- `0x140001828`
- `0x140001acc`
- `0x140002004`
- `0x1400020e4`
- `0x140002188`
- `0x140002274`
- `0x140002338`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001fec`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001fec`

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
0x140001f60  sub     rsp, 48h
0x140001f64  movzx   eax, byte ptr [rdx]
0x140001f67  mov     r11, rcx
0x140001f6a  shl     eax, 18h
0x140001f6d  mov     r10, r8
0x140001f70  mov     r8, [rsp+48h+arg_28]
0x140001f75  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001f79  movzx   eax, word ptr [rdx+1]
0x140001f7d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001f81  mov     rax, [rdx+3]
0x140001f85  add     rdx, 0Bh
0x140001f89  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001f8e  mov     rax, [rcx+8]
0x140001f92  mov     [r8], rax
0x140001f95  mov     rax, [rcx+8]
0x140001f99  mov     [rsp+48h+UserData], r8; UserData
0x140001f9e  movzx   ecx, word ptr [rax]
0x140001fa1  mov     [r8+8], ecx
0x140001fa5  lea     rcx, _TraceLoggingMetadata
0x140001fac  mov     [r8+10h], rdx
0x140001fb0  mov     dword ptr [r8+0Ch], 2
0x140001fb8  movzx   eax, word ptr [rdx]
0x140001fbb  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001fc0  mov     [r8+18h], eax
0x140001fc4  lea     rax, _TraceLoggingMetadataEnd
0x140001fcb  sub     eax, ecx
0x140001fcd  mov     dword ptr [r8+1Ch], 1
0x140001fd5  mov     dword ptr [rsp+48h+arg_28], eax
0x140001fd9  mov     r8, r10; ActivityId
0x140001fdc  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001fe0  mov     eax, [rsp+48h+arg_20]
0x140001fe4  mov     rcx, [r11+20h]; RegHandle
0x140001fe8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001fec  call    cs:__imp_EventWriteTransfer
0x140001ff3  nop     dword ptr [rax+rax+00h]
0x140001ff8  add     rsp, 48h
0x140001ffc  retn
```
