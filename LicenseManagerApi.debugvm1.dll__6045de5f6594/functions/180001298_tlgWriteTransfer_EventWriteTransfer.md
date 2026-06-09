# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001298`
- end: `0x18000132f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x18000110c`
- `0x1800011d4`
- `0x180010420`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001324`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001324`

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
0x180001298  sub     rsp, 48h
0x18000129c  movzx   eax, byte ptr [rdx]
0x18000129f  mov     r11, rcx
0x1800012a2  shl     eax, 18h
0x1800012a5  mov     r10, r8
0x1800012a8  mov     r8, [rsp+48h+arg_28]
0x1800012ad  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800012b1  movzx   eax, word ptr [rdx+1]
0x1800012b5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800012b9  mov     rax, [rdx+3]
0x1800012bd  add     rdx, 0Bh
0x1800012c1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800012c6  mov     rax, [rcx+8]
0x1800012ca  mov     [r8], rax
0x1800012cd  mov     rax, [rcx+8]
0x1800012d1  mov     [rsp+48h+UserData], r8; UserData
0x1800012d6  movzx   ecx, word ptr [rax]
0x1800012d9  mov     [r8+8], ecx
0x1800012dd  lea     rcx, _TraceLoggingMetadata
0x1800012e4  mov     [r8+10h], rdx
0x1800012e8  mov     dword ptr [r8+0Ch], 2
0x1800012f0  movzx   eax, word ptr [rdx]
0x1800012f3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800012f8  mov     [r8+18h], eax
0x1800012fc  lea     rax, _TraceLoggingMetadataEnd
0x180001303  sub     eax, ecx
0x180001305  mov     dword ptr [r8+1Ch], 1
0x18000130d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001311  mov     r8, r10; ActivityId
0x180001314  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001318  mov     eax, [rsp+48h+arg_20]
0x18000131c  mov     rcx, [r11+20h]; RegHandle
0x180001320  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001324  call    cs:__imp_EventWriteTransfer
0x18000132a  add     rsp, 48h
0x18000132e  retn
```
