# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000ad0c`
- end: `0x18000adb0`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `164`
- prototype: `__int64 __fastcall(int, int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18002c3d4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ad9e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ad9e`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_EventWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
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
  UserData->Ptr = (ULONGLONG)off_1800A4440;
  UserData->Size = *(unsigned __int16 *)off_1800A4440;
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData->Reserved = 2;
  UserData[1].Size = *v7;
  UserData[1].Reserved = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, UserData);
}

```

## disassembly

```asm
0x18000ad0c  sub     rsp, 48h
0x18000ad10  movzx   eax, byte ptr [rdx]
0x18000ad13  xor     r9d, r9d; RelatedActivityId
0x18000ad16  mov     r8, [rsp+48h+arg_28]
0x18000ad1b  shl     eax, 18h
0x18000ad1e  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000ad22  movzx   eax, word ptr [rdx+1]
0x18000ad26  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000ad2a  mov     rax, [rdx+3]
0x18000ad2e  add     rdx, 0Bh
0x18000ad32  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000ad37  mov     rax, cs:off_1800A4440
0x18000ad3e  mov     [r8], rax
0x18000ad41  mov     rax, cs:off_1800A4440
0x18000ad48  mov     [rsp+48h+UserData], r8; UserData
0x18000ad4d  mov     [rsp+48h+UserDataCount], 5; UserDataCount
0x18000ad55  movzx   ecx, word ptr [rax]
0x18000ad58  mov     [r8+8], ecx
0x18000ad5c  lea     rcx, _TraceLoggingMetadata
0x18000ad63  mov     [r8+10h], rdx
0x18000ad67  mov     dword ptr [r8+0Ch], 2
0x18000ad6f  movzx   eax, word ptr [rdx]
0x18000ad72  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000ad77  mov     [r8+18h], eax
0x18000ad7b  lea     rax, _TraceLoggingMetadataEnd
0x18000ad82  sub     eax, ecx
0x18000ad84  mov     dword ptr [r8+1Ch], 1
0x18000ad8c  mov     [rsp+48h+arg_20], eax
0x18000ad90  xor     r8d, r8d; ActivityId
0x18000ad93  mov     eax, [rsp+48h+arg_20]
0x18000ad97  mov     rcx, cs:RegHandle; RegHandle
0x18000ad9e  call    cs:__imp_EventWriteTransfer
0x18000ada5  nop     dword ptr [rax+rax+00h]
0x18000adaa  add     rsp, 48h
0x18000adae  retn
```
