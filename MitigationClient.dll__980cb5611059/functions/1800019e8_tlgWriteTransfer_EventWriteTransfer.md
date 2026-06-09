# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800019e8`
- end: `0x180001a7f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `24`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800012b8`
- `0x18000156c`
- `0x180001a88`
- `0x180001b7c`
- `0x180001bec`
- `0x180001c7c`
- `0x180001e00`
- `0x180001fac`
- `0x1800020b0`
- `0x180002174`
- `0x18000223c`
- `0x180002388`
- `0x180002644`
- `0x1800027b8`
- `0x180002964`
- `0x180002ab0`
- `0x180002bec`
- `0x180003050`
- `0x180003130`
- `0x18001716c`
- `0x1800192c4`
- `0x18001b7bc`
- `0x180041224`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001a74`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001a74`

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
0x1800019e8  sub     rsp, 48h
0x1800019ec  movzx   eax, byte ptr [rdx]
0x1800019ef  mov     r11, rcx
0x1800019f2  shl     eax, 18h
0x1800019f5  mov     r10, r8
0x1800019f8  mov     r8, [rsp+48h+arg_28]
0x1800019fd  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001a01  movzx   eax, word ptr [rdx+1]
0x180001a05  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001a09  mov     rax, [rdx+3]
0x180001a0d  add     rdx, 0Bh
0x180001a11  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001a16  mov     rax, [rcx+8]
0x180001a1a  mov     [r8], rax
0x180001a1d  mov     rax, [rcx+8]
0x180001a21  mov     [rsp+48h+UserData], r8; UserData
0x180001a26  movzx   ecx, word ptr [rax]
0x180001a29  mov     [r8+8], ecx
0x180001a2d  lea     rcx, _TraceLoggingMetadata
0x180001a34  mov     [r8+10h], rdx
0x180001a38  mov     dword ptr [r8+0Ch], 2
0x180001a40  movzx   eax, word ptr [rdx]
0x180001a43  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001a48  mov     [r8+18h], eax
0x180001a4c  lea     rax, _TraceLoggingMetadataEnd
0x180001a53  sub     eax, ecx
0x180001a55  mov     dword ptr [r8+1Ch], 1
0x180001a5d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001a61  mov     r8, r10; ActivityId
0x180001a64  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001a68  mov     eax, [rsp+48h+arg_20]
0x180001a6c  mov     rcx, [r11+20h]; RegHandle
0x180001a70  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001a74  call    cs:__imp_EventWriteTransfer
0x180001a7a  add     rsp, 48h
0x180001a7e  retn
```
