# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000ce50`
- end: `0x18000ceee`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x1800010c4`
- `0x18000110c`
- `0x18000148c`
- `0x1800015b4`
- `0x1800018ac`
- `0x180001a38`
- `0x180001ae4`
- `0x180001ca0`
- `0x180002244`
- `0x180002534`
- `0x180002834`
- `0x180002b5c`
- `0x180002ec0`
- `0x1800031d8`
- `0x18000329c`
- `0x18000337c`
- `0x180003450`
- `0x1800034e4`
- `0x1800036bc`
- `0x180003d14`
- `0x180003ddc`
- `0x1800040a4`
- `0x180004138`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cedc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cedc`

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
0x18000ce50  sub     rsp, 48h
0x18000ce54  movzx   eax, byte ptr [rdx]
0x18000ce57  mov     r11, rcx
0x18000ce5a  shl     eax, 18h
0x18000ce5d  mov     r10, r8
0x18000ce60  mov     r8, [rsp+48h+arg_28]
0x18000ce65  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000ce69  movzx   eax, word ptr [rdx+1]
0x18000ce6d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000ce71  mov     rax, [rdx+3]
0x18000ce75  add     rdx, 0Bh
0x18000ce79  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000ce7e  mov     rax, [rcx+8]
0x18000ce82  mov     [r8], rax
0x18000ce85  mov     rax, [rcx+8]
0x18000ce89  mov     [rsp+48h+UserData], r8; UserData
0x18000ce8e  movzx   ecx, word ptr [rax]
0x18000ce91  mov     [r8+8], ecx
0x18000ce95  lea     rcx, _TraceLoggingMetadata
0x18000ce9c  mov     [r8+10h], rdx
0x18000cea0  mov     dword ptr [r8+0Ch], 2
0x18000cea8  movzx   eax, word ptr [rdx]
0x18000ceab  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000ceb0  mov     [r8+18h], eax
0x18000ceb4  lea     rax, _TraceLoggingMetadataEnd
0x18000cebb  sub     eax, ecx
0x18000cebd  mov     dword ptr [r8+1Ch], 1
0x18000cec5  mov     dword ptr [rsp+48h+arg_28], eax
0x18000cec9  mov     r8, r10; ActivityId
0x18000cecc  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000ced0  mov     eax, [rsp+48h+arg_20]
0x18000ced4  mov     rcx, [r11+20h]; RegHandle
0x18000ced8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000cedc  call    cs:__imp_EventWriteTransfer
0x18000cee3  nop     dword ptr [rax+rax+00h]
0x18000cee8  add     rsp, 48h
0x18000ceec  retn
```
