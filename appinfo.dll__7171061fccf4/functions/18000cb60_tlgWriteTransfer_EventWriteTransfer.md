# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000cb60`
- end: `0x18000cbf7`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `26`
- callee_count: `0`
- tags: ``

## callers

- `0x1800010b8`
- `0x180001100`
- `0x18000147c`
- `0x1800015a4`
- `0x1800018c0`
- `0x180001a4c`
- `0x180001bec`
- `0x180001ce4`
- `0x180001d90`
- `0x180001f48`
- `0x1800024e4`
- `0x1800027d0`
- `0x180002acc`
- `0x180002e30`
- `0x180003144`
- `0x180003204`
- `0x1800032e4`
- `0x1800033b8`
- `0x18000358c`
- `0x180003bdc`
- `0x180003ca4`
- `0x180003f68`
- `0x180003ff8`
- `0x180013720`
- `0x180014690`
- `0x180017528`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cbec`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cbec`

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
0x18000cb60  sub     rsp, 48h
0x18000cb64  movzx   eax, byte ptr [rdx]
0x18000cb67  mov     r11, rcx
0x18000cb6a  shl     eax, 18h
0x18000cb6d  mov     r10, r8
0x18000cb70  mov     r8, [rsp+48h+arg_28]
0x18000cb75  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000cb79  movzx   eax, word ptr [rdx+1]
0x18000cb7d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000cb81  mov     rax, [rdx+3]
0x18000cb85  add     rdx, 0Bh
0x18000cb89  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000cb8e  mov     rax, [rcx+8]
0x18000cb92  mov     [r8], rax
0x18000cb95  mov     rax, [rcx+8]
0x18000cb99  mov     [rsp+48h+UserData], r8; UserData
0x18000cb9e  movzx   ecx, word ptr [rax]
0x18000cba1  mov     [r8+8], ecx
0x18000cba5  lea     rcx, _TraceLoggingMetadata
0x18000cbac  mov     [r8+10h], rdx
0x18000cbb0  mov     dword ptr [r8+0Ch], 2
0x18000cbb8  movzx   eax, word ptr [rdx]
0x18000cbbb  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000cbc0  mov     [r8+18h], eax
0x18000cbc4  lea     rax, _TraceLoggingMetadataEnd
0x18000cbcb  sub     eax, ecx
0x18000cbcd  mov     dword ptr [r8+1Ch], 1
0x18000cbd5  mov     dword ptr [rsp+48h+arg_28], eax
0x18000cbd9  mov     r8, r10; ActivityId
0x18000cbdc  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000cbe0  mov     eax, [rsp+48h+arg_20]
0x18000cbe4  mov     rcx, [r11+20h]; RegHandle
0x18000cbe8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000cbec  call    cs:__imp_EventWriteTransfer
0x18000cbf2  add     rsp, 48h
0x18000cbf6  retn
```
