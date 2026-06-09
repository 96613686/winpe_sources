# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x14000176c`
- end: `0x140001803`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `27`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x1400012bc`
- `0x140001360`
- `0x1400013ec`
- `0x14000180c`
- `0x140001968`
- `0x140001c2c`
- `0x140005668`
- `0x140005740`
- `0x140005bfc`
- `0x14000a84c`
- `0x14000a930`
- `0x14000aa08`
- `0x14000aaec`
- `0x14000ad94`
- `0x14000ae78`
- `0x14000be9c`
- `0x14000bf74`
- `0x14000c04c`
- `0x14000c124`
- `0x14000c1fc`
- `0x14000c2d4`
- `0x140014a20`
- `0x140015e08`
- `0x140015f50`
- `0x140018dc4`
- `0x140019314`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400017f8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400017f8`

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
0x14000176c  sub     rsp, 48h
0x140001770  movzx   eax, byte ptr [rdx]
0x140001773  mov     r11, rcx
0x140001776  shl     eax, 18h
0x140001779  mov     r10, r8
0x14000177c  mov     r8, [rsp+48h+arg_28]
0x140001781  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001785  movzx   eax, word ptr [rdx+1]
0x140001789  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x14000178d  mov     rax, [rdx+3]
0x140001791  add     rdx, 0Bh
0x140001795  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x14000179a  mov     rax, [rcx+8]
0x14000179e  mov     [r8], rax
0x1400017a1  mov     rax, [rcx+8]
0x1400017a5  mov     [rsp+48h+UserData], r8; UserData
0x1400017aa  movzx   ecx, word ptr [rax]
0x1400017ad  mov     [r8+8], ecx
0x1400017b1  lea     rcx, _TraceLoggingMetadata
0x1400017b8  mov     [r8+10h], rdx
0x1400017bc  mov     dword ptr [r8+0Ch], 2
0x1400017c4  movzx   eax, word ptr [rdx]
0x1400017c7  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1400017cc  mov     [r8+18h], eax
0x1400017d0  lea     rax, _TraceLoggingMetadataEnd
0x1400017d7  sub     eax, ecx
0x1400017d9  mov     dword ptr [r8+1Ch], 1
0x1400017e1  mov     dword ptr [rsp+48h+arg_28], eax
0x1400017e5  mov     r8, r10; ActivityId
0x1400017e8  mov     eax, dword ptr [rsp+48h+arg_28]
0x1400017ec  mov     eax, [rsp+48h+arg_20]
0x1400017f0  mov     rcx, [r11+20h]; RegHandle
0x1400017f4  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400017f8  call    cs:__imp_EventWriteTransfer
0x1400017fe  add     rsp, 48h
0x140001802  retn
```
