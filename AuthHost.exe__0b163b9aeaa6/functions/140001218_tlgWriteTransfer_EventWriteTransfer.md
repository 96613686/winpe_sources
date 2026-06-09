# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001218`
- end: `0x1400012af`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14000116c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400012a4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400012a4`

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
0x140001218  sub     rsp, 48h
0x14000121c  movzx   eax, byte ptr [rdx]
0x14000121f  mov     r11, rcx
0x140001222  shl     eax, 18h
0x140001225  mov     r10, r8
0x140001228  mov     r8, [rsp+48h+arg_28]
0x14000122d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001231  movzx   eax, word ptr [rdx+1]
0x140001235  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001239  mov     rax, [rdx+3]
0x14000123d  add     rdx, 0Bh
0x140001241  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001246  mov     rax, [rcx+8]
0x14000124a  mov     [r8], rax
0x14000124d  mov     rax, [rcx+8]
0x140001251  mov     [rsp+48h+UserData], r8; UserData
0x140001256  movzx   ecx, word ptr [rax]
0x140001259  mov     [r8+8], ecx
0x14000125d  lea     rcx, _TraceLoggingMetadata
0x140001264  mov     [r8+10h], rdx
0x140001268  mov     dword ptr [r8+0Ch], 2
0x140001270  movzx   eax, word ptr [rdx]
0x140001273  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001278  mov     [r8+18h], eax
0x14000127c  lea     rax, _TraceLoggingMetadataEnd
0x140001283  sub     eax, ecx
0x140001285  mov     dword ptr [r8+1Ch], 1
0x14000128d  mov     dword ptr [rsp+48h+arg_28], eax
0x140001291  mov     r8, r10; ActivityId
0x140001294  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001298  mov     eax, [rsp+48h+arg_20]
0x14000129c  mov     rcx, [r11+20h]; RegHandle
0x1400012a0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400012a4  call    cs:__imp_EventWriteTransfer
0x1400012aa  add     rsp, 48h
0x1400012ae  retn
```
