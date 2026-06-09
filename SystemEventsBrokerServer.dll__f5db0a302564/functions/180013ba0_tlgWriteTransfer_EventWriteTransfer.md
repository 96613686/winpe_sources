# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180013ba0`
- end: `0x180013c37`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x18000142c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013c2c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013c2c`

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
0x180013ba0  sub     rsp, 48h
0x180013ba4  movzx   eax, byte ptr [rdx]
0x180013ba7  mov     r11, rcx
0x180013baa  shl     eax, 18h
0x180013bad  mov     r10, r8
0x180013bb0  mov     r8, [rsp+48h+arg_28]
0x180013bb5  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180013bb9  movzx   eax, word ptr [rdx+1]
0x180013bbd  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180013bc1  mov     rax, [rdx+3]
0x180013bc5  add     rdx, 0Bh
0x180013bc9  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180013bce  mov     rax, [rcx+8]
0x180013bd2  mov     [r8], rax
0x180013bd5  mov     rax, [rcx+8]
0x180013bd9  mov     [rsp+48h+UserData], r8; UserData
0x180013bde  movzx   ecx, word ptr [rax]
0x180013be1  mov     [r8+8], ecx
0x180013be5  lea     rcx, _TraceLoggingMetadata
0x180013bec  mov     [r8+10h], rdx
0x180013bf0  mov     dword ptr [r8+0Ch], 2
0x180013bf8  movzx   eax, word ptr [rdx]
0x180013bfb  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180013c00  mov     [r8+18h], eax
0x180013c04  lea     rax, _TraceLoggingMetadataEnd
0x180013c0b  sub     eax, ecx
0x180013c0d  mov     dword ptr [r8+1Ch], 1
0x180013c15  mov     dword ptr [rsp+48h+arg_28], eax
0x180013c19  mov     r8, r10; ActivityId
0x180013c1c  mov     eax, dword ptr [rsp+48h+arg_28]
0x180013c20  mov     eax, [rsp+48h+arg_20]
0x180013c24  mov     rcx, [r11+20h]; RegHandle
0x180013c28  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180013c2c  call    cs:__imp_EventWriteTransfer
0x180013c32  add     rsp, 48h
0x180013c36  retn
```
