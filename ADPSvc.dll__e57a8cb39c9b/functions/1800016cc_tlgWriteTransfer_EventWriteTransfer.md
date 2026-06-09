# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800016cc`
- end: `0x180001763`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x180001098`
- `0x18000134c`
- `0x18000176c`
- `0x180011f94`
- `0x18002a990`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001758`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001758`

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
0x1800016cc  sub     rsp, 48h
0x1800016d0  movzx   eax, byte ptr [rdx]
0x1800016d3  mov     r11, rcx
0x1800016d6  shl     eax, 18h
0x1800016d9  mov     r10, r8
0x1800016dc  mov     r8, [rsp+48h+arg_28]
0x1800016e1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800016e5  movzx   eax, word ptr [rdx+1]
0x1800016e9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800016ed  mov     rax, [rdx+3]
0x1800016f1  add     rdx, 0Bh
0x1800016f5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800016fa  mov     rax, [rcx+8]
0x1800016fe  mov     [r8], rax
0x180001701  mov     rax, [rcx+8]
0x180001705  mov     [rsp+48h+UserData], r8; UserData
0x18000170a  movzx   ecx, word ptr [rax]
0x18000170d  mov     [r8+8], ecx
0x180001711  lea     rcx, _TraceLoggingMetadata
0x180001718  mov     [r8+10h], rdx
0x18000171c  mov     dword ptr [r8+0Ch], 2
0x180001724  movzx   eax, word ptr [rdx]
0x180001727  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000172c  mov     [r8+18h], eax
0x180001730  lea     rax, _TraceLoggingMetadataEnd
0x180001737  sub     eax, ecx
0x180001739  mov     dword ptr [r8+1Ch], 1
0x180001741  mov     dword ptr [rsp+48h+arg_28], eax
0x180001745  mov     r8, r10; ActivityId
0x180001748  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000174c  mov     eax, [rsp+48h+arg_20]
0x180001750  mov     rcx, [r11+20h]; RegHandle
0x180001754  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001758  call    cs:__imp_EventWriteTransfer
0x18000175e  add     rsp, 48h
0x180001762  retn
```
