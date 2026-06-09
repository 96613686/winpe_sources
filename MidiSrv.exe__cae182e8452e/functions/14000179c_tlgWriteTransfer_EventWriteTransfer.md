# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x14000179c`
- end: `0x140001833`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `51`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x140001094`
- `0x14000116c`
- `0x140001420`
- `0x14000183c`
- `0x1400018e4`
- `0x1400019d8`
- `0x140001ad4`
- `0x140001bc0`
- `0x140001ce8`
- `0x140001e00`
- `0x140001f28`
- `0x14000204c`
- `0x140002184`
- `0x140002270`
- `0x140002390`
- `0x140002490`
- `0x140002580`
- `0x140002670`
- `0x140002734`
- `0x140002858`
- `0x14000298c`
- `0x140002adc`
- `0x140002ca8`
- `0x140002e24`
- `0x140002f48`
- `0x14000307c`
- `0x14000317c`
- `0x1400032f0`
- `0x140003400`
- `0x140003500`
- `0x140003640`
- `0x14000a0cc`
- `0x14000b1f0`
- `0x14000b2b8`
- `0x140010068`
- `0x140018f54`
- `0x1400193c4`
- `0x14001bf60`
- `0x140029640`
- `0x140030250`
- `0x140030b10`
- `0x140032ff4`
- `0x140034f50`
- `0x1400399d0`
- `0x14003b820`
- `0x14003bad0`
- `0x1400457ec`
- `0x140045eb4`
- `0x140046048`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001828`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001828`

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
0x14000179c  sub     rsp, 48h
0x1400017a0  movzx   eax, byte ptr [rdx]
0x1400017a3  mov     r11, rcx
0x1400017a6  shl     eax, 18h
0x1400017a9  mov     r10, r8
0x1400017ac  mov     r8, [rsp+48h+arg_28]
0x1400017b1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1400017b5  movzx   eax, word ptr [rdx+1]
0x1400017b9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1400017bd  mov     rax, [rdx+3]
0x1400017c1  add     rdx, 0Bh
0x1400017c5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1400017ca  mov     rax, [rcx+8]
0x1400017ce  mov     [r8], rax
0x1400017d1  mov     rax, [rcx+8]
0x1400017d5  mov     [rsp+48h+UserData], r8; UserData
0x1400017da  movzx   ecx, word ptr [rax]
0x1400017dd  mov     [r8+8], ecx
0x1400017e1  lea     rcx, _TraceLoggingMetadata
0x1400017e8  mov     [r8+10h], rdx
0x1400017ec  mov     dword ptr [r8+0Ch], 2
0x1400017f4  movzx   eax, word ptr [rdx]
0x1400017f7  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1400017fc  mov     [r8+18h], eax
0x140001800  lea     rax, _TraceLoggingMetadataEnd
0x140001807  sub     eax, ecx
0x140001809  mov     dword ptr [r8+1Ch], 1
0x140001811  mov     dword ptr [rsp+48h+arg_28], eax
0x140001815  mov     r8, r10; ActivityId
0x140001818  mov     eax, dword ptr [rsp+48h+arg_28]
0x14000181c  mov     eax, [rsp+48h+arg_20]
0x140001820  mov     rcx, [r11+20h]; RegHandle
0x140001824  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001828  call    cs:__imp_EventWriteTransfer
0x14000182e  add     rsp, 48h
0x140001832  retn
```
