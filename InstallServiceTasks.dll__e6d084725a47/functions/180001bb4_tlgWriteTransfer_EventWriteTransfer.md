# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001bb4`
- end: `0x180001c4b`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x18000116c`
- `0x180001444`
- `0x180001518`
- `0x1800015dc`
- `0x180001890`
- `0x180001c54`
- `0x180001cfc`
- `0x180001f3c`
- `0x180002030`
- `0x180033c24`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001c40`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001c40`

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
0x180001bb4  sub     rsp, 48h
0x180001bb8  movzx   eax, byte ptr [rdx]
0x180001bbb  mov     r11, rcx
0x180001bbe  shl     eax, 18h
0x180001bc1  mov     r10, r8
0x180001bc4  mov     r8, [rsp+48h+arg_28]
0x180001bc9  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001bcd  movzx   eax, word ptr [rdx+1]
0x180001bd1  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001bd5  mov     rax, [rdx+3]
0x180001bd9  add     rdx, 0Bh
0x180001bdd  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001be2  mov     rax, [rcx+8]
0x180001be6  mov     [r8], rax
0x180001be9  mov     rax, [rcx+8]
0x180001bed  mov     [rsp+48h+UserData], r8; UserData
0x180001bf2  movzx   ecx, word ptr [rax]
0x180001bf5  mov     [r8+8], ecx
0x180001bf9  lea     rcx, _TraceLoggingMetadata
0x180001c00  mov     [r8+10h], rdx
0x180001c04  mov     dword ptr [r8+0Ch], 2
0x180001c0c  movzx   eax, word ptr [rdx]
0x180001c0f  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001c14  mov     [r8+18h], eax
0x180001c18  lea     rax, _TraceLoggingMetadataEnd
0x180001c1f  sub     eax, ecx
0x180001c21  mov     dword ptr [r8+1Ch], 1
0x180001c29  mov     dword ptr [rsp+48h+arg_28], eax
0x180001c2d  mov     r8, r10; ActivityId
0x180001c30  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001c34  mov     eax, [rsp+48h+arg_20]
0x180001c38  mov     rcx, [r11+20h]; RegHandle
0x180001c3c  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001c40  call    cs:__imp_EventWriteTransfer
0x180001c46  add     rsp, 48h
0x180001c4a  retn
```
