# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000163c`
- end: `0x1800016d3`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180009a9c`
- `0x180009be0`
- `0x18000f2ac`
- `0x18000ff54`
- `0x1800110c0`
- `0x180011408`
- `0x180016db0`
- `0x180017278`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800016c8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800016c8`

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
0x18000163c  sub     rsp, 48h
0x180001640  movzx   eax, byte ptr [rdx]
0x180001643  mov     r11, rcx
0x180001646  shl     eax, 18h
0x180001649  mov     r10, r8
0x18000164c  mov     r8, [rsp+48h+arg_28]
0x180001651  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001655  movzx   eax, word ptr [rdx+1]
0x180001659  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000165d  mov     rax, [rdx+3]
0x180001661  add     rdx, 0Bh
0x180001665  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000166a  mov     rax, [rcx+8]
0x18000166e  mov     [r8], rax
0x180001671  mov     rax, [rcx+8]
0x180001675  mov     [rsp+48h+UserData], r8; UserData
0x18000167a  movzx   ecx, word ptr [rax]
0x18000167d  mov     [r8+8], ecx
0x180001681  lea     rcx, _TraceLoggingMetadata
0x180001688  mov     [r8+10h], rdx
0x18000168c  mov     dword ptr [r8+0Ch], 2
0x180001694  movzx   eax, word ptr [rdx]
0x180001697  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000169c  mov     [r8+18h], eax
0x1800016a0  lea     rax, _TraceLoggingMetadataEnd
0x1800016a7  sub     eax, ecx
0x1800016a9  mov     dword ptr [r8+1Ch], 1
0x1800016b1  mov     dword ptr [rsp+48h+arg_28], eax
0x1800016b5  mov     r8, r10; ActivityId
0x1800016b8  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800016bc  mov     eax, [rsp+48h+arg_20]
0x1800016c0  mov     rcx, [r11+20h]; RegHandle
0x1800016c4  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800016c8  call    cs:__imp_EventWriteTransfer
0x1800016ce  add     rsp, 48h
0x1800016d2  retn
```
