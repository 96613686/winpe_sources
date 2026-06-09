# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001010`
- end: `0x1800010a7`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `35`
- callee_count: `0`
- tags: ``

## callers

- `0x1800010dc`
- `0x1800011c4`
- `0x18000120c`
- `0x180001650`
- `0x1800018bc`
- `0x18000198c`
- `0x180001a7c`
- `0x180001b28`
- `0x180001c70`
- `0x180001d8c`
- `0x180001ef4`
- `0x180001f90`
- `0x180002040`
- `0x180002198`
- `0x180002318`
- `0x1800023d4`
- `0x18000249c`
- `0x18000263c`
- `0x180002844`
- `0x1800029b4`
- `0x180002ac8`
- `0x180002bcc`
- `0x180002c90`
- `0x180002d9c`
- `0x180002ea0`
- `0x18000341c`
- `0x1800036d0`
- `0x1800039e4`
- `0x180003a54`
- `0x180003ae4`
- `0x180003be0`
- `0x180003e84`
- `0x180012340`
- `0x180015e28`
- `0x18001d1b0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000109c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000109c`

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
0x180001010  sub     rsp, 48h
0x180001014  movzx   eax, byte ptr [rdx]
0x180001017  mov     r11, rcx
0x18000101a  shl     eax, 18h
0x18000101d  mov     r10, r8
0x180001020  mov     r8, [rsp+48h+arg_28]
0x180001025  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001029  movzx   eax, word ptr [rdx+1]
0x18000102d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001031  mov     rax, [rdx+3]
0x180001035  add     rdx, 0Bh
0x180001039  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000103e  mov     rax, [rcx+8]
0x180001042  mov     [r8], rax
0x180001045  mov     rax, [rcx+8]
0x180001049  mov     [rsp+48h+UserData], r8; UserData
0x18000104e  movzx   ecx, word ptr [rax]
0x180001051  mov     [r8+8], ecx
0x180001055  lea     rcx, _TraceLoggingMetadata
0x18000105c  mov     [r8+10h], rdx
0x180001060  mov     dword ptr [r8+0Ch], 2
0x180001068  movzx   eax, word ptr [rdx]
0x18000106b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001070  mov     [r8+18h], eax
0x180001074  lea     rax, _TraceLoggingMetadataEnd
0x18000107b  sub     eax, ecx
0x18000107d  mov     dword ptr [r8+1Ch], 1
0x180001085  mov     dword ptr [rsp+48h+arg_28], eax
0x180001089  mov     r8, r10; ActivityId
0x18000108c  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001090  mov     eax, [rsp+48h+arg_20]
0x180001094  mov     rcx, [r11+20h]; RegHandle
0x180001098  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000109c  call    cs:__imp_EventWriteTransfer
0x1800010a2  add     rsp, 48h
0x1800010a6  retn
```
