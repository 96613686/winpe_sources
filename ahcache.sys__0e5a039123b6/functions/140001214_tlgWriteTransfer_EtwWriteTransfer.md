# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001214`
- end: `0x1400012b2`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `158`
- prototype: `NTSTATUS __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400012a0`
- `ntoskrnl!EtwWriteTransfer` at `0x1400012a0`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteTransfer_EtwWriteTransfer(
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
  return EtwWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140001214  sub     rsp, 48h
0x140001218  movzx   eax, byte ptr [rdx]
0x14000121b  mov     r11, rcx
0x14000121e  shl     eax, 18h
0x140001221  mov     r10, r8
0x140001224  mov     r8, [rsp+48h+arg_28]
0x140001229  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x14000122d  movzx   eax, word ptr [rdx+1]
0x140001231  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001235  mov     rax, [rdx+3]
0x140001239  add     rdx, 0Bh
0x14000123d  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001242  mov     rax, [rcx+8]
0x140001246  mov     [r8], rax
0x140001249  mov     rax, [rcx+8]
0x14000124d  mov     [rsp+48h+UserData], r8; UserData
0x140001252  movzx   ecx, word ptr [rax]
0x140001255  mov     [r8+8], ecx
0x140001259  lea     rcx, _TraceLoggingMetadata
0x140001260  mov     [r8+10h], rdx
0x140001264  mov     dword ptr [r8+0Ch], 2
0x14000126c  movzx   eax, word ptr [rdx]
0x14000126f  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001274  mov     [r8+18h], eax
0x140001278  lea     rax, _TraceLoggingMetadataEnd
0x14000127f  sub     eax, ecx
0x140001281  mov     dword ptr [r8+1Ch], 1
0x140001289  mov     dword ptr [rsp+48h+arg_28], eax
0x14000128d  mov     r8, r10; ActivityId
0x140001290  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001294  mov     eax, [rsp+48h+arg_20]
0x140001298  mov     rcx, [r11+20h]; RegHandle
0x14000129c  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400012a0  call    cs:__imp_EtwWriteTransfer
0x1400012a7  nop     dword ptr [rax+rax+00h]
0x1400012ac  add     rsp, 48h
0x1400012b0  retn
```
