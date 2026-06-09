# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001ad8`
- end: `0x180001b6f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `26`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800012b8`
- `0x1800013a4`
- `0x180001658`
- `0x180001b78`
- `0x180001c0c`
- `0x180001cd0`
- `0x180001d18`
- `0x180001ddc`
- `0x1800020f0`
- `0x180002160`
- `0x1800021f0`
- `0x1800022ec`
- `0x1800023f4`
- `0x1800024e0`
- `0x1800025a0`
- `0x1800027cc`
- `0x1800028f4`
- `0x180002a18`
- `0x180002c24`
- `0x180002d3c`
- `0x180002e54`
- `0x180002fc4`
- `0x1800031ac`
- `0x18000c9b0`
- `0x180013980`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001b64`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001b64`

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
0x180001ad8  sub     rsp, 48h
0x180001adc  movzx   eax, byte ptr [rdx]
0x180001adf  mov     r11, rcx
0x180001ae2  shl     eax, 18h
0x180001ae5  mov     r10, r8
0x180001ae8  mov     r8, [rsp+48h+arg_28]
0x180001aed  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001af1  movzx   eax, word ptr [rdx+1]
0x180001af5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001af9  mov     rax, [rdx+3]
0x180001afd  add     rdx, 0Bh
0x180001b01  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001b06  mov     rax, [rcx+8]
0x180001b0a  mov     [r8], rax
0x180001b0d  mov     rax, [rcx+8]
0x180001b11  mov     [rsp+48h+UserData], r8; UserData
0x180001b16  movzx   ecx, word ptr [rax]
0x180001b19  mov     [r8+8], ecx
0x180001b1d  lea     rcx, _TraceLoggingMetadata
0x180001b24  mov     [r8+10h], rdx
0x180001b28  mov     dword ptr [r8+0Ch], 2
0x180001b30  movzx   eax, word ptr [rdx]
0x180001b33  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001b38  mov     [r8+18h], eax
0x180001b3c  lea     rax, _TraceLoggingMetadataEnd
0x180001b43  sub     eax, ecx
0x180001b45  mov     dword ptr [r8+1Ch], 1
0x180001b4d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001b51  mov     r8, r10; ActivityId
0x180001b54  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001b58  mov     eax, [rsp+48h+arg_20]
0x180001b5c  mov     rcx, [r11+20h]; RegHandle
0x180001b60  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001b64  call    cs:__imp_EventWriteTransfer
0x180001b6a  add     rsp, 48h
0x180001b6e  retn
```
