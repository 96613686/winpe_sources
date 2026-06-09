# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x14000162c`
- end: `0x1400016c3`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x140001098`
- `0x140001178`
- `0x140001270`
- `0x14000131c`
- `0x1400013f0`
- `0x1400016cc`
- `0x1400019a4`
- `0x140001a68`
- `0x140001d1c`
- `0x140005464`
- `0x14000560c`
- `0x140005f98`
- `0x140008ce4`
- `0x14000964c`
- `0x140009da0`
- `0x14000a804`
- `0x14000b354`
- `0x14000b70c`
- `0x14000be08`
- `0x14000c798`
- `0x140017360`
- `0x14001a8bc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400016b8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400016b8`

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
0x14000162c  sub     rsp, 48h
0x140001630  movzx   eax, byte ptr [rdx]
0x140001633  mov     r11, rcx
0x140001636  shl     eax, 18h
0x140001639  mov     r10, r8
0x14000163c  mov     r8, [rsp+48h+arg_28]
0x140001641  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001645  movzx   eax, word ptr [rdx+1]
0x140001649  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x14000164d  mov     rax, [rdx+3]
0x140001651  add     rdx, 0Bh
0x140001655  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x14000165a  mov     rax, [rcx+8]
0x14000165e  mov     [r8], rax
0x140001661  mov     rax, [rcx+8]
0x140001665  mov     [rsp+48h+UserData], r8; UserData
0x14000166a  movzx   ecx, word ptr [rax]
0x14000166d  mov     [r8+8], ecx
0x140001671  lea     rcx, _TraceLoggingMetadata
0x140001678  mov     [r8+10h], rdx
0x14000167c  mov     dword ptr [r8+0Ch], 2
0x140001684  movzx   eax, word ptr [rdx]
0x140001687  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x14000168c  mov     [r8+18h], eax
0x140001690  lea     rax, _TraceLoggingMetadataEnd
0x140001697  sub     eax, ecx
0x140001699  mov     dword ptr [r8+1Ch], 1
0x1400016a1  mov     dword ptr [rsp+48h+arg_28], eax
0x1400016a5  mov     r8, r10; ActivityId
0x1400016a8  mov     eax, dword ptr [rsp+48h+arg_28]
0x1400016ac  mov     eax, [rsp+48h+arg_20]
0x1400016b0  mov     rcx, [r11+20h]; RegHandle
0x1400016b4  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400016b8  call    cs:__imp_EventWriteTransfer
0x1400016be  add     rsp, 48h
0x1400016c2  retn
```
