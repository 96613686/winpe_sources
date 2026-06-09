# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18001a5bc`
- end: `0x18001a653`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x18000110c`
- `0x180001200`
- `0x1800012c4`
- `0x180001368`
- `0x1800013fc`
- `0x1800016b0`
- `0x1800019cc`
- `0x180001a7c`
- `0x180001af4`
- `0x180001dc8`
- `0x180001e58`
- `0x180001f2c`
- `0x180001f8c`
- `0x180002058`
- `0x18000212c`
- `0x1800167e8`
- `0x18001a010`
- `0x18001a0d8`
- `0x18001a1dc`
- `0x18001a480`
- `0x18001a548`
- `0x1800211b0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001a648`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001a648`

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
0x18001a5bc  sub     rsp, 48h
0x18001a5c0  movzx   eax, byte ptr [rdx]
0x18001a5c3  mov     r11, rcx
0x18001a5c6  shl     eax, 18h
0x18001a5c9  mov     r10, r8
0x18001a5cc  mov     r8, [rsp+48h+arg_28]
0x18001a5d1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18001a5d5  movzx   eax, word ptr [rdx+1]
0x18001a5d9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18001a5dd  mov     rax, [rdx+3]
0x18001a5e1  add     rdx, 0Bh
0x18001a5e5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18001a5ea  mov     rax, [rcx+8]
0x18001a5ee  mov     [r8], rax
0x18001a5f1  mov     rax, [rcx+8]
0x18001a5f5  mov     [rsp+48h+UserData], r8; UserData
0x18001a5fa  movzx   ecx, word ptr [rax]
0x18001a5fd  mov     [r8+8], ecx
0x18001a601  lea     rcx, _TraceLoggingMetadata
0x18001a608  mov     [r8+10h], rdx
0x18001a60c  mov     dword ptr [r8+0Ch], 2
0x18001a614  movzx   eax, word ptr [rdx]
0x18001a617  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18001a61c  mov     [r8+18h], eax
0x18001a620  lea     rax, _TraceLoggingMetadataEnd
0x18001a627  sub     eax, ecx
0x18001a629  mov     dword ptr [r8+1Ch], 1
0x18001a631  mov     dword ptr [rsp+48h+arg_28], eax
0x18001a635  mov     r8, r10; ActivityId
0x18001a638  mov     eax, dword ptr [rsp+48h+arg_28]
0x18001a63c  mov     eax, [rsp+48h+arg_20]
0x18001a640  mov     rcx, [r11+20h]; RegHandle
0x18001a644  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18001a648  call    cs:__imp_EventWriteTransfer
0x18001a64e  add     rsp, 48h
0x18001a652  retn
```
