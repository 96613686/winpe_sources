# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001b20`
- end: `0x180001bbe`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `60`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x180001160`
- `0x180001280`
- `0x1800013c8`
- `0x18000167c`
- `0x180001bc4`
- `0x180001cec`
- `0x180001df8`
- `0x180001f14`
- `0x18000203c`
- `0x180002178`
- `0x1800022f4`
- `0x180002458`
- `0x180002590`
- `0x1800027b8`
- `0x1800028f4`
- `0x180002a40`
- `0x180002b90`
- `0x180002cf4`
- `0x180002e40`
- `0x180002fa0`
- `0x180003114`
- `0x1800032f0`
- `0x180003468`
- `0x1800035f8`
- `0x180003744`
- `0x1800038a4`
- `0x180003a18`
- `0x180003bc0`
- `0x180003d80`
- `0x18000402c`
- `0x180004138`
- `0x1800041fc`
- `0x1800042d0`
- `0x1800043a4`
- `0x180004484`
- `0x180004588`
- `0x1800046c4`
- `0x180004810`
- `0x18000495c`
- `0x180004ad0`
- `0x180004c5c`
- `0x180004d68`
- `0x180004fa8`
- `0x1800050e4`
- `0x18000523c`
- `0x1800053a8`
- `0x18000551c`
- `0x180005658`
- `0x180005784`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001bac`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001bac`

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
0x180001b20  sub     rsp, 48h
0x180001b24  movzx   eax, byte ptr [rdx]
0x180001b27  mov     r11, rcx
0x180001b2a  shl     eax, 18h
0x180001b2d  mov     r10, r8
0x180001b30  mov     r8, [rsp+48h+arg_28]
0x180001b35  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001b39  movzx   eax, word ptr [rdx+1]
0x180001b3d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001b41  mov     rax, [rdx+3]
0x180001b45  add     rdx, 0Bh
0x180001b49  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001b4e  mov     rax, [rcx+8]
0x180001b52  mov     [r8], rax
0x180001b55  mov     rax, [rcx+8]
0x180001b59  mov     [rsp+48h+UserData], r8; UserData
0x180001b5e  movzx   ecx, word ptr [rax]
0x180001b61  mov     [r8+8], ecx
0x180001b65  lea     rcx, _TraceLoggingMetadata
0x180001b6c  mov     [r8+10h], rdx
0x180001b70  mov     dword ptr [r8+0Ch], 2
0x180001b78  movzx   eax, word ptr [rdx]
0x180001b7b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001b80  mov     [r8+18h], eax
0x180001b84  lea     rax, _TraceLoggingMetadataEnd
0x180001b8b  sub     eax, ecx
0x180001b8d  mov     dword ptr [r8+1Ch], 1
0x180001b95  mov     dword ptr [rsp+48h+arg_28], eax
0x180001b99  mov     r8, r10; ActivityId
0x180001b9c  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001ba0  mov     eax, [rsp+48h+arg_20]
0x180001ba4  mov     rcx, [r11+20h]; RegHandle
0x180001ba8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001bac  call    cs:__imp_EventWriteTransfer
0x180001bb3  nop     dword ptr [rax+rax+00h]
0x180001bb8  add     rsp, 48h
0x180001bbc  retn
```
