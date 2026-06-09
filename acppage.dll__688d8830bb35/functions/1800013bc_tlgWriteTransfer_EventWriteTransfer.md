# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800013bc`
- end: `0x180001453`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x18001010c`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180001448`
- `ADVAPI32!EventWriteTransfer` at `0x180001448`

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
0x1800013bc  sub     rsp, 48h
0x1800013c0  movzx   eax, byte ptr [rdx]
0x1800013c3  mov     r11, rcx
0x1800013c6  shl     eax, 18h
0x1800013c9  mov     r10, r8
0x1800013cc  mov     r8, [rsp+48h+arg_28]
0x1800013d1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800013d5  movzx   eax, word ptr [rdx+1]
0x1800013d9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800013dd  mov     rax, [rdx+3]
0x1800013e1  add     rdx, 0Bh
0x1800013e5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800013ea  mov     rax, [rcx+8]
0x1800013ee  mov     [r8], rax
0x1800013f1  mov     rax, [rcx+8]
0x1800013f5  mov     [rsp+48h+UserData], r8; UserData
0x1800013fa  movzx   ecx, word ptr [rax]
0x1800013fd  mov     [r8+8], ecx
0x180001401  lea     rcx, _TraceLoggingMetadata
0x180001408  mov     [r8+10h], rdx
0x18000140c  mov     dword ptr [r8+0Ch], 2
0x180001414  movzx   eax, word ptr [rdx]
0x180001417  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000141c  mov     [r8+18h], eax
0x180001420  lea     rax, _TraceLoggingMetadataEnd
0x180001427  sub     eax, ecx
0x180001429  mov     dword ptr [r8+1Ch], 1
0x180001431  mov     dword ptr [rsp+48h+arg_28], eax
0x180001435  mov     r8, r10; ActivityId
0x180001438  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000143c  mov     eax, [rsp+48h+arg_20]
0x180001440  mov     rcx, [r11+20h]; RegHandle
0x180001444  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001448  call    cs:__imp_EventWriteTransfer
0x18000144e  add     rsp, 48h
0x180001452  retn
```
