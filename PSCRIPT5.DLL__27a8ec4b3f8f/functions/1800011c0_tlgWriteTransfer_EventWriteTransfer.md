# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800011c0`
- end: `0x18000125e`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001264`
- `0x18000133c`
- `0x1800015f0`
- `0x18000a268`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x18000124c`
- `ADVAPI32!EventWriteTransfer` at `0x18000124c`

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
  unsigned __int8 *v7; // rdx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = a2 + 11;
  EventDescriptor.Keyword = v6;
  UserData->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData->Reserved = 2;
  UserData[1].Size = *(unsigned __int16 *)v7;
  UserData[1].Reserved = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800011c0  sub     rsp, 48h
0x1800011c4  movzx   eax, byte ptr [rdx]
0x1800011c7  mov     r11, rcx
0x1800011ca  shl     eax, 18h
0x1800011cd  mov     r10, r8
0x1800011d0  mov     r8, [rsp+48h+arg_28]
0x1800011d5  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800011d9  movzx   eax, word ptr [rdx+1]
0x1800011dd  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800011e1  mov     rax, [rdx+3]
0x1800011e5  add     rdx, 0Bh
0x1800011e9  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800011ee  mov     rax, [rcx+8]
0x1800011f2  mov     [r8], rax
0x1800011f5  mov     rax, [rcx+8]
0x1800011f9  mov     [rsp+48h+UserData], r8; UserData
0x1800011fe  movzx   ecx, word ptr [rax]
0x180001201  mov     [r8+8], ecx
0x180001205  lea     rcx, _TraceLoggingMetadata
0x18000120c  mov     [r8+10h], rdx
0x180001210  mov     dword ptr [r8+0Ch], 2
0x180001218  movzx   eax, word ptr [rdx]
0x18000121b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001220  mov     [r8+18h], eax
0x180001224  lea     rax, _TraceLoggingMetadataEnd
0x18000122b  sub     eax, ecx
0x18000122d  mov     dword ptr [r8+1Ch], 1
0x180001235  mov     dword ptr [rsp+48h+arg_28], eax
0x180001239  mov     r8, r10; ActivityId
0x18000123c  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001240  mov     eax, [rsp+48h+arg_20]
0x180001244  mov     rcx, [r11+20h]; RegHandle
0x180001248  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000124c  call    cs:__imp_EventWriteTransfer
0x180001253  nop     dword ptr [rax+rax+00h]
0x180001258  add     rsp, 48h
0x18000125c  retn
```
