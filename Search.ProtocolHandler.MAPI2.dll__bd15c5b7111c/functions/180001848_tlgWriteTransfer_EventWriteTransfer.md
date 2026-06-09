# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001848`
- end: `0x1800018df`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x180001110`
- `0x1800013c4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800018d4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800018d4`

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
0x180001848  sub     rsp, 48h
0x18000184c  movzx   eax, byte ptr [rdx]
0x18000184f  mov     r11, rcx
0x180001852  shl     eax, 18h
0x180001855  mov     r10, r8
0x180001858  mov     r8, [rsp+48h+arg_28]
0x18000185d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001861  movzx   eax, word ptr [rdx+1]
0x180001865  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001869  mov     rax, [rdx+3]
0x18000186d  add     rdx, 0Bh
0x180001871  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001876  mov     rax, [rcx+8]
0x18000187a  mov     [r8], rax
0x18000187d  mov     rax, [rcx+8]
0x180001881  mov     [rsp+48h+UserData], r8; UserData
0x180001886  movzx   ecx, word ptr [rax]
0x180001889  mov     [r8+8], ecx
0x18000188d  lea     rcx, _TraceLoggingMetadata
0x180001894  mov     [r8+10h], rdx
0x180001898  mov     dword ptr [r8+0Ch], 2
0x1800018a0  movzx   eax, word ptr [rdx]
0x1800018a3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800018a8  mov     [r8+18h], eax
0x1800018ac  lea     rax, _TraceLoggingMetadataEnd
0x1800018b3  sub     eax, ecx
0x1800018b5  mov     dword ptr [r8+1Ch], 1
0x1800018bd  mov     dword ptr [rsp+48h+arg_28], eax
0x1800018c1  mov     r8, r10; ActivityId
0x1800018c4  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800018c8  mov     eax, [rsp+48h+arg_20]
0x1800018cc  mov     rcx, [r11+20h]; RegHandle
0x1800018d0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800018d4  call    cs:__imp_EventWriteTransfer
0x1800018da  add     rsp, 48h
0x1800018de  retn
```
