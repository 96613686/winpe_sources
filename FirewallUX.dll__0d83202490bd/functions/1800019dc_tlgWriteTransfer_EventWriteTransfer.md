# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800019dc`
- end: `0x180001a73`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `37`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800015d0`
- `0x180001660`
- `0x180001a7c`
- `0x180004bb4`
- `0x18000fdd0`
- `0x1800123e0`
- `0x180012eb8`
- `0x180013344`
- `0x1800139a4`
- `0x1800176e4`
- `0x180018360`
- `0x180018648`
- `0x180019ec0`
- `0x18001aaf0`
- `0x18001ab70`
- `0x18001abf0`
- `0x18001aca4`
- `0x18001ad24`
- `0x18001ada4`
- `0x18001ae24`
- `0x18001aea4`
- `0x18001af58`
- `0x18001afd8`
- `0x18001b08c`
- `0x18001b764`
- `0x18001cdc0`
- `0x18001de64`
- `0x18001f27c`
- `0x18001f53c`
- `0x18001f6f4`
- `0x180020088`
- `0x18002028c`
- `0x1800209d4`
- `0x1800229a0`
- `0x180028ab4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001a68`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001a68`

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
0x1800019dc  sub     rsp, 48h
0x1800019e0  movzx   eax, byte ptr [rdx]
0x1800019e3  mov     r11, rcx
0x1800019e6  shl     eax, 18h
0x1800019e9  mov     r10, r8
0x1800019ec  mov     r8, [rsp+48h+arg_28]
0x1800019f1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800019f5  movzx   eax, word ptr [rdx+1]
0x1800019f9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800019fd  mov     rax, [rdx+3]
0x180001a01  add     rdx, 0Bh
0x180001a05  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001a0a  mov     rax, [rcx+8]
0x180001a0e  mov     [r8], rax
0x180001a11  mov     rax, [rcx+8]
0x180001a15  mov     [rsp+48h+UserData], r8; UserData
0x180001a1a  movzx   ecx, word ptr [rax]
0x180001a1d  mov     [r8+8], ecx
0x180001a21  lea     rcx, _TraceLoggingMetadata
0x180001a28  mov     [r8+10h], rdx
0x180001a2c  mov     dword ptr [r8+0Ch], 2
0x180001a34  movzx   eax, word ptr [rdx]
0x180001a37  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001a3c  mov     [r8+18h], eax
0x180001a40  lea     rax, _TraceLoggingMetadataEnd
0x180001a47  sub     eax, ecx
0x180001a49  mov     dword ptr [r8+1Ch], 1
0x180001a51  mov     dword ptr [rsp+48h+arg_28], eax
0x180001a55  mov     r8, r10; ActivityId
0x180001a58  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001a5c  mov     eax, [rsp+48h+arg_20]
0x180001a60  mov     rcx, [r11+20h]; RegHandle
0x180001a64  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001a68  call    cs:__imp_EventWriteTransfer
0x180001a6e  add     rsp, 48h
0x180001a72  retn
```
