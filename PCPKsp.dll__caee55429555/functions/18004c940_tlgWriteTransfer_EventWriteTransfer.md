# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18004c940`
- end: `0x18004c9de`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x18000142c`
- `0x180001524`
- `0x1800015d0`
- `0x180001630`
- `0x1800018e4`
- `0x180001bf8`
- `0x180001ca4`
- `0x180001d84`
- `0x18004c72c`
- `0x18004c7c8`
- `0x18005d000`
- `0x18007bc30`
- `0x18007feb8`
- `0x180090988`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004c9cc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004c9cc`

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
0x18004c940  sub     rsp, 48h
0x18004c944  movzx   eax, byte ptr [rdx]
0x18004c947  mov     r11, rcx
0x18004c94a  shl     eax, 18h
0x18004c94d  mov     r10, r8
0x18004c950  mov     r8, [rsp+48h+arg_28]
0x18004c955  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18004c959  movzx   eax, word ptr [rdx+1]
0x18004c95d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18004c961  mov     rax, [rdx+3]
0x18004c965  add     rdx, 0Bh
0x18004c969  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18004c96e  mov     rax, [rcx+8]
0x18004c972  mov     [r8], rax
0x18004c975  mov     rax, [rcx+8]
0x18004c979  mov     [rsp+48h+UserData], r8; UserData
0x18004c97e  movzx   ecx, word ptr [rax]
0x18004c981  mov     [r8+8], ecx
0x18004c985  lea     rcx, _TraceLoggingMetadata
0x18004c98c  mov     [r8+10h], rdx
0x18004c990  mov     dword ptr [r8+0Ch], 2
0x18004c998  movzx   eax, word ptr [rdx]
0x18004c99b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18004c9a0  mov     [r8+18h], eax
0x18004c9a4  lea     rax, _TraceLoggingMetadataEnd
0x18004c9ab  sub     eax, ecx
0x18004c9ad  mov     dword ptr [r8+1Ch], 1
0x18004c9b5  mov     dword ptr [rsp+48h+arg_28], eax
0x18004c9b9  mov     r8, r10; ActivityId
0x18004c9bc  mov     eax, dword ptr [rsp+48h+arg_28]
0x18004c9c0  mov     eax, [rsp+48h+arg_20]
0x18004c9c4  mov     rcx, [r11+20h]; RegHandle
0x18004c9c8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18004c9cc  call    cs:__imp_EventWriteTransfer
0x18004c9d3  nop     dword ptr [rax+rax+00h]
0x18004c9d8  add     rsp, 48h
0x18004c9dc  retn
```
