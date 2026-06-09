# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001874`
- end: `0x18000190b`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180001178`
- `0x180001224`
- `0x1800012e0`
- `0x1800013ac`
- `0x180001488`
- `0x18000158c`
- `0x1800016c0`
- `0x180005554`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001900`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001900`

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
0x180001874  sub     rsp, 48h
0x180001878  movzx   eax, byte ptr [rdx]
0x18000187b  mov     r11, rcx
0x18000187e  shl     eax, 18h
0x180001881  mov     r10, r8
0x180001884  mov     r8, [rsp+48h+arg_28]
0x180001889  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000188d  movzx   eax, word ptr [rdx+1]
0x180001891  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001895  mov     rax, [rdx+3]
0x180001899  add     rdx, 0Bh
0x18000189d  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800018a2  mov     rax, [rcx+8]
0x1800018a6  mov     [r8], rax
0x1800018a9  mov     rax, [rcx+8]
0x1800018ad  mov     [rsp+48h+UserData], r8; UserData
0x1800018b2  movzx   ecx, word ptr [rax]
0x1800018b5  mov     [r8+8], ecx
0x1800018b9  lea     rcx, _TraceLoggingMetadata
0x1800018c0  mov     [r8+10h], rdx
0x1800018c4  mov     dword ptr [r8+0Ch], 2
0x1800018cc  movzx   eax, word ptr [rdx]
0x1800018cf  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800018d4  mov     [r8+18h], eax
0x1800018d8  lea     rax, _TraceLoggingMetadataEnd
0x1800018df  sub     eax, ecx
0x1800018e1  mov     dword ptr [r8+1Ch], 1
0x1800018e9  mov     dword ptr [rsp+48h+arg_28], eax
0x1800018ed  mov     r8, r10; ActivityId
0x1800018f0  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800018f4  mov     eax, [rsp+48h+arg_20]
0x1800018f8  mov     rcx, [r11+20h]; RegHandle
0x1800018fc  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001900  call    cs:__imp_EventWriteTransfer
0x180001906  add     rsp, 48h
0x18000190a  retn
```
