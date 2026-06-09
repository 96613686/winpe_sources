# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001bc0`
- end: `0x140001c57`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1400010bc`
- `0x1400090cc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001c4c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001c4c`

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
0x140001bc0  sub     rsp, 48h
0x140001bc4  movzx   eax, byte ptr [rdx]
0x140001bc7  mov     r11, rcx
0x140001bca  shl     eax, 18h
0x140001bcd  mov     r10, r8
0x140001bd0  mov     r8, [rsp+48h+arg_28]
0x140001bd5  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001bd9  movzx   eax, word ptr [rdx+1]
0x140001bdd  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001be1  mov     rax, [rdx+3]
0x140001be5  add     rdx, 0Bh
0x140001be9  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001bee  mov     rax, [rcx+8]
0x140001bf2  mov     [r8], rax
0x140001bf5  mov     rax, [rcx+8]
0x140001bf9  mov     [rsp+48h+UserData], r8; UserData
0x140001bfe  movzx   ecx, word ptr [rax]
0x140001c01  mov     [r8+8], ecx
0x140001c05  lea     rcx, _TraceLoggingMetadata
0x140001c0c  mov     [r8+10h], rdx
0x140001c10  mov     dword ptr [r8+0Ch], 2
0x140001c18  movzx   eax, word ptr [rdx]
0x140001c1b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001c20  mov     [r8+18h], eax
0x140001c24  lea     rax, _TraceLoggingMetadataEnd
0x140001c2b  sub     eax, ecx
0x140001c2d  mov     dword ptr [r8+1Ch], 1
0x140001c35  mov     dword ptr [rsp+48h+arg_28], eax
0x140001c39  mov     r8, r10; ActivityId
0x140001c3c  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001c40  mov     eax, [rsp+48h+arg_20]
0x140001c44  mov     rcx, [r11+20h]; RegHandle
0x140001c48  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001c4c  call    cs:__imp_EventWriteTransfer
0x140001c52  add     rsp, 48h
0x140001c56  retn
```
