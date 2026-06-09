# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000194c`
- end: `0x1800019e3`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800015b4`
- `0x180001a9c`
- `0x18000c490`
- `0x18000c590`
- `0x180011678`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800019d8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800019d8`

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
0x18000194c  sub     rsp, 48h
0x180001950  movzx   eax, byte ptr [rdx]
0x180001953  mov     r11, rcx
0x180001956  shl     eax, 18h
0x180001959  mov     r10, r8
0x18000195c  mov     r8, [rsp+48h+arg_28]
0x180001961  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001965  movzx   eax, word ptr [rdx+1]
0x180001969  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000196d  mov     rax, [rdx+3]
0x180001971  add     rdx, 0Bh
0x180001975  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000197a  mov     rax, [rcx+8]
0x18000197e  mov     [r8], rax
0x180001981  mov     rax, [rcx+8]
0x180001985  mov     [rsp+48h+UserData], r8; UserData
0x18000198a  movzx   ecx, word ptr [rax]
0x18000198d  mov     [r8+8], ecx
0x180001991  lea     rcx, _TraceLoggingMetadata
0x180001998  mov     [r8+10h], rdx
0x18000199c  mov     dword ptr [r8+0Ch], 2
0x1800019a4  movzx   eax, word ptr [rdx]
0x1800019a7  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800019ac  mov     [r8+18h], eax
0x1800019b0  lea     rax, _TraceLoggingMetadataEnd
0x1800019b7  sub     eax, ecx
0x1800019b9  mov     dword ptr [r8+1Ch], 1
0x1800019c1  mov     dword ptr [rsp+48h+arg_28], eax
0x1800019c5  mov     r8, r10; ActivityId
0x1800019c8  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800019cc  mov     eax, [rsp+48h+arg_20]
0x1800019d0  mov     rcx, [r11+20h]; RegHandle
0x1800019d4  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800019d8  call    cs:__imp_EventWriteTransfer
0x1800019de  add     rsp, 48h
0x1800019e2  retn
```
