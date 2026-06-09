# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000120c`
- end: `0x1800012a3`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800010d0`
- `0x180002c64`
- `0x180002d18`
- `0x180002ec0`
- `0x180002fc0`
- `0x180003098`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001298`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001298`

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
0x18000120c  sub     rsp, 48h
0x180001210  movzx   eax, byte ptr [rdx]
0x180001213  mov     r11, rcx
0x180001216  shl     eax, 18h
0x180001219  mov     r10, r8
0x18000121c  mov     r8, [rsp+48h+arg_28]
0x180001221  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001225  movzx   eax, word ptr [rdx+1]
0x180001229  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000122d  mov     rax, [rdx+3]
0x180001231  add     rdx, 0Bh
0x180001235  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000123a  mov     rax, [rcx+8]
0x18000123e  mov     [r8], rax
0x180001241  mov     rax, [rcx+8]
0x180001245  mov     [rsp+48h+UserData], r8; UserData
0x18000124a  movzx   ecx, word ptr [rax]
0x18000124d  mov     [r8+8], ecx
0x180001251  lea     rcx, _TraceLoggingMetadata
0x180001258  mov     [r8+10h], rdx
0x18000125c  mov     dword ptr [r8+0Ch], 2
0x180001264  movzx   eax, word ptr [rdx]
0x180001267  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000126c  mov     [r8+18h], eax
0x180001270  lea     rax, _TraceLoggingMetadataEnd
0x180001277  sub     eax, ecx
0x180001279  mov     dword ptr [r8+1Ch], 1
0x180001281  mov     dword ptr [rsp+48h+arg_28], eax
0x180001285  mov     r8, r10; ActivityId
0x180001288  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000128c  mov     eax, [rsp+48h+arg_20]
0x180001290  mov     rcx, [r11+20h]; RegHandle
0x180001294  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001298  call    cs:__imp_EventWriteTransfer
0x18000129e  add     rsp, 48h
0x1800012a2  retn
```
