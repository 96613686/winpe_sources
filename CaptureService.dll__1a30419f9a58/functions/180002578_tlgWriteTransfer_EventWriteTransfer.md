# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180002578`
- end: `0x18000260f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800010dc`
- `0x180001124`
- `0x1800011d0`
- `0x180001484`
- `0x180001770`
- `0x180001a84`
- `0x180001b14`
- `0x180001bd4`
- `0x180001cb4`
- `0x180001f58`
- `0x180002250`
- `0x180002314`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002604`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002604`

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
0x180002578  sub     rsp, 48h
0x18000257c  movzx   eax, byte ptr [rdx]
0x18000257f  mov     r11, rcx
0x180002582  shl     eax, 18h
0x180002585  mov     r10, r8
0x180002588  mov     r8, [rsp+48h+arg_28]
0x18000258d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180002591  movzx   eax, word ptr [rdx+1]
0x180002595  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180002599  mov     rax, [rdx+3]
0x18000259d  add     rdx, 0Bh
0x1800025a1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800025a6  mov     rax, [rcx+8]
0x1800025aa  mov     [r8], rax
0x1800025ad  mov     rax, [rcx+8]
0x1800025b1  mov     [rsp+48h+UserData], r8; UserData
0x1800025b6  movzx   ecx, word ptr [rax]
0x1800025b9  mov     [r8+8], ecx
0x1800025bd  lea     rcx, _TraceLoggingMetadata
0x1800025c4  mov     [r8+10h], rdx
0x1800025c8  mov     dword ptr [r8+0Ch], 2
0x1800025d0  movzx   eax, word ptr [rdx]
0x1800025d3  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800025d8  mov     [r8+18h], eax
0x1800025dc  lea     rax, _TraceLoggingMetadataEnd
0x1800025e3  sub     eax, ecx
0x1800025e5  mov     dword ptr [r8+1Ch], 1
0x1800025ed  mov     dword ptr [rsp+48h+arg_28], eax
0x1800025f1  mov     r8, r10; ActivityId
0x1800025f4  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800025f8  mov     eax, [rsp+48h+arg_20]
0x1800025fc  mov     rcx, [r11+20h]; RegHandle
0x180002600  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180002604  call    cs:__imp_EventWriteTransfer
0x18000260a  add     rsp, 48h
0x18000260e  retn
```
