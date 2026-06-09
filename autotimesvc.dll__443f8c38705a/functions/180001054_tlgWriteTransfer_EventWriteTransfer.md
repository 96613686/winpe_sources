# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001054`
- end: `0x1800010eb`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `33`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800010f4`
- `0x180001150`
- `0x180001218`
- `0x180001270`
- `0x18000131c`
- `0x1800013ac`
- `0x180001428`
- `0x18000148c`
- `0x180001524`
- `0x1800015c0`
- `0x180001670`
- `0x1800016f0`
- `0x18000178c`
- `0x180001838`
- `0x1800018b4`
- `0x180001934`
- `0x180001d9c`
- `0x180001e7c`
- `0x180001f74`
- `0x180002020`
- `0x18000211c`
- `0x1800021e4`
- `0x1800022ac`
- `0x180002370`
- `0x180002440`
- `0x1800061ac`
- `0x18000743c`
- `0x180007534`
- `0x18000b668`
- `0x18000bd34`
- `0x18000c720`
- `0x18000cc10`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800010e0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800010e0`

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
0x180001054  sub     rsp, 48h
0x180001058  movzx   eax, byte ptr [rdx]
0x18000105b  mov     r11, rcx
0x18000105e  shl     eax, 18h
0x180001061  mov     r10, r8
0x180001064  mov     r8, [rsp+48h+arg_28]
0x180001069  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000106d  movzx   eax, word ptr [rdx+1]
0x180001071  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001075  mov     rax, [rdx+3]
0x180001079  add     rdx, 0Bh
0x18000107d  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001082  mov     rax, [rcx+8]
0x180001086  mov     [r8], rax
0x180001089  mov     rax, [rcx+8]
0x18000108d  mov     [rsp+48h+UserData], r8; UserData
0x180001092  movzx   ecx, word ptr [rax]
0x180001095  mov     [r8+8], ecx
0x180001099  lea     rcx, _TraceLoggingMetadata
0x1800010a0  mov     [r8+10h], rdx
0x1800010a4  mov     dword ptr [r8+0Ch], 2
0x1800010ac  movzx   eax, word ptr [rdx]
0x1800010af  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800010b4  mov     [r8+18h], eax
0x1800010b8  lea     rax, _TraceLoggingMetadataEnd
0x1800010bf  sub     eax, ecx
0x1800010c1  mov     dword ptr [r8+1Ch], 1
0x1800010c9  mov     dword ptr [rsp+48h+arg_28], eax
0x1800010cd  mov     r8, r10; ActivityId
0x1800010d0  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800010d4  mov     eax, [rsp+48h+arg_20]
0x1800010d8  mov     rcx, [r11+20h]; RegHandle
0x1800010dc  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800010e0  call    cs:__imp_EventWriteTransfer
0x1800010e6  add     rsp, 48h
0x1800010ea  retn
```
