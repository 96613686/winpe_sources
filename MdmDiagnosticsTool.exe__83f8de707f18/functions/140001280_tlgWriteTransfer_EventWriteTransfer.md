# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001280`
- end: `0x14000131e`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x14000104c`
- `0x140009938`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000130c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000130c`

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
0x140001280  sub     rsp, 48h
0x140001284  movzx   eax, byte ptr [rdx]
0x140001287  mov     r11, rcx
0x14000128a  shl     eax, 18h
0x14000128d  mov     r10, r8
0x140001290  mov     r8, [rsp+48h+arg_28]
0x140001295  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001299  movzx   eax, word ptr [rdx+1]
0x14000129d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1400012a1  mov     rax, [rdx+3]
0x1400012a5  add     rdx, 0Bh
0x1400012a9  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1400012ae  mov     rax, [rcx+8]
0x1400012b2  mov     [r8], rax
0x1400012b5  mov     rax, [rcx+8]
0x1400012b9  mov     [rsp+48h+UserData], r8; UserData
0x1400012be  movzx   ecx, word ptr [rax]
0x1400012c1  mov     [r8+8], ecx
0x1400012c5  lea     rcx, _TraceLoggingMetadata
0x1400012cc  mov     [r8+10h], rdx
0x1400012d0  mov     dword ptr [r8+0Ch], 2
0x1400012d8  movzx   eax, word ptr [rdx]
0x1400012db  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1400012e0  mov     [r8+18h], eax
0x1400012e4  lea     rax, _TraceLoggingMetadataEnd
0x1400012eb  sub     eax, ecx
0x1400012ed  mov     dword ptr [r8+1Ch], 1
0x1400012f5  mov     dword ptr [rsp+48h+arg_28], eax
0x1400012f9  mov     r8, r10; ActivityId
0x1400012fc  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001300  mov     eax, [rsp+48h+arg_20]
0x140001304  mov     rcx, [r11+20h]; RegHandle
0x140001308  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x14000130c  call    cs:__imp_EventWriteTransfer
0x140001313  nop     dword ptr [rax+rax+00h]
0x140001318  add     rsp, 48h
0x14000131c  retn
```
