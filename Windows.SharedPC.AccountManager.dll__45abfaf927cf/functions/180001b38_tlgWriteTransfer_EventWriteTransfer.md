# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001b38`
- end: `0x180001bcf`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800012cc`
- `0x180001314`
- `0x180001384`
- `0x180001410`
- `0x1800016b4`
- `0x180001bd8`
- `0x180001c38`
- `0x180001cc8`
- `0x180001fe0`
- `0x1800020c0`
- `0x180002384`
- `0x180002414`
- `0x1800026ec`
- `0x18000278c`
- `0x180002a60`
- `0x180002dac`
- `0x18001f78c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001bc4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001bc4`

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
0x180001b38  sub     rsp, 48h
0x180001b3c  movzx   eax, byte ptr [rdx]
0x180001b3f  mov     r11, rcx
0x180001b42  shl     eax, 18h
0x180001b45  mov     r10, r8
0x180001b48  mov     r8, [rsp+48h+arg_28]
0x180001b4d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001b51  movzx   eax, word ptr [rdx+1]
0x180001b55  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001b59  mov     rax, [rdx+3]
0x180001b5d  add     rdx, 0Bh
0x180001b61  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001b66  mov     rax, [rcx+8]
0x180001b6a  mov     [r8], rax
0x180001b6d  mov     rax, [rcx+8]
0x180001b71  mov     [rsp+48h+UserData], r8; UserData
0x180001b76  movzx   ecx, word ptr [rax]
0x180001b79  mov     [r8+8], ecx
0x180001b7d  lea     rcx, _TraceLoggingMetadata
0x180001b84  mov     [r8+10h], rdx
0x180001b88  mov     dword ptr [r8+0Ch], 2
0x180001b90  movzx   eax, word ptr [rdx]
0x180001b93  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001b98  mov     [r8+18h], eax
0x180001b9c  lea     rax, _TraceLoggingMetadataEnd
0x180001ba3  sub     eax, ecx
0x180001ba5  mov     dword ptr [r8+1Ch], 1
0x180001bad  mov     dword ptr [rsp+48h+arg_28], eax
0x180001bb1  mov     r8, r10; ActivityId
0x180001bb4  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001bb8  mov     eax, [rsp+48h+arg_20]
0x180001bbc  mov     rcx, [r11+20h]; RegHandle
0x180001bc0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001bc4  call    cs:__imp_EventWriteTransfer
0x180001bca  add     rsp, 48h
0x180001bce  retn
```
