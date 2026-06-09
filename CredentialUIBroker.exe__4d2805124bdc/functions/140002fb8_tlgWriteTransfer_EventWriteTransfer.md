# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140002fb8`
- end: `0x14000304f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `22`
- callee_count: `0`
- tags: ``

## callers

- `0x140001010`
- `0x140001304`
- `0x14000134c`
- `0x1400013f8`
- `0x1400014c0`
- `0x14000156c`
- `0x140001640`
- `0x140001704`
- `0x14000177c`
- `0x140001a30`
- `0x140001d70`
- `0x14000205c`
- `0x140002370`
- `0x1400023e0`
- `0x140002470`
- `0x140002554`
- `0x140002614`
- `0x1400026f4`
- `0x140002998`
- `0x140002c90`
- `0x140002d54`
- `0x140005128`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x140003044`
- `ADVAPI32!EventWriteTransfer` at `0x140003044`

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
0x140002fb8  sub     rsp, 48h
0x140002fbc  movzx   eax, byte ptr [rdx]
0x140002fbf  mov     r11, rcx
0x140002fc2  shl     eax, 18h
0x140002fc5  mov     r10, r8
0x140002fc8  mov     r8, [rsp+48h+arg_28]
0x140002fcd  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140002fd1  movzx   eax, word ptr [rdx+1]
0x140002fd5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140002fd9  mov     rax, [rdx+3]
0x140002fdd  add     rdx, 0Bh
0x140002fe1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140002fe6  mov     rax, [rcx+8]
0x140002fea  mov     [r8], rax
0x140002fed  mov     rax, [rcx+8]
0x140002ff1  mov     [rsp+48h+UserData], r8; UserData
0x140002ff6  movzx   ecx, word ptr [rax]
0x140002ff9  mov     [r8+8], ecx
0x140002ffd  lea     rcx, _TraceLoggingMetadata
0x140003004  mov     [r8+10h], rdx
0x140003008  mov     dword ptr [r8+0Ch], 2
0x140003010  movzx   eax, word ptr [rdx]
0x140003013  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140003018  mov     [r8+18h], eax
0x14000301c  lea     rax, _TraceLoggingMetadataEnd
0x140003023  sub     eax, ecx
0x140003025  mov     dword ptr [r8+1Ch], 1
0x14000302d  mov     dword ptr [rsp+48h+arg_28], eax
0x140003031  mov     r8, r10; ActivityId
0x140003034  mov     eax, dword ptr [rsp+48h+arg_28]
0x140003038  mov     eax, [rsp+48h+arg_20]
0x14000303c  mov     rcx, [r11+20h]; RegHandle
0x140003040  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140003044  call    cs:__imp_EventWriteTransfer
0x14000304a  add     rsp, 48h
0x14000304e  retn
```
