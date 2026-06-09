# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001430`
- end: `0x1400014ce`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `158`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x14000bea0`
- `0x14000c18c`
- `0x14000c5b0`
- `0x14000c6f0`
- `0x14000d040`
- `0x14001202c`
- `0x140012450`
- `0x140012c84`
- `0x140012eec`
- `0x140013c7c`
- `0x140014180`
- `0x140014648`
- `0x14001474c`
- `0x140014f90`
- `0x140015608`
- `0x140015878`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400014bc`
- `ntoskrnl!EtwWriteTransfer` at `0x1400014bc`

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
0x140001430  sub     rsp, 48h
0x140001434  movzx   eax, byte ptr [rdx]
0x140001437  mov     r11, rcx
0x14000143a  shl     eax, 18h
0x14000143d  mov     r10, r8
0x140001440  mov     r8, [rsp+48h+arg_28]
0x140001445  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001449  movzx   eax, word ptr [rdx+1]
0x14000144d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001451  mov     rax, [rdx+3]
0x140001455  add     rdx, 0Bh
0x140001459  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x14000145e  mov     rax, [rcx+8]
0x140001462  mov     [r8], rax
0x140001465  mov     rax, [rcx+8]
0x140001469  mov     [rsp+48h+UserData], r8; UserData
0x14000146e  movzx   ecx, word ptr [rax]
0x140001471  mov     [r8+8], ecx
0x140001475  lea     rcx, _TraceLoggingMetadata
0x14000147c  mov     [r8+10h], rdx
0x140001480  mov     dword ptr [r8+0Ch], 2
0x140001488  movzx   eax, word ptr [rdx]
0x14000148b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001490  mov     [r8+18h], eax
0x140001494  lea     rax, _TraceLoggingMetadataEnd
0x14000149b  sub     eax, ecx
0x14000149d  mov     dword ptr [r8+1Ch], 1
0x1400014a5  mov     dword ptr [rsp+48h+arg_28], eax
0x1400014a9  mov     r8, r10; ActivityId
0x1400014ac  mov     eax, dword ptr [rsp+48h+arg_28]
0x1400014b0  mov     eax, [rsp+48h+arg_20]
0x1400014b4  mov     rcx, [r11+20h]; RegHandle
0x1400014b8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400014bc  call    cs:__imp_EtwWriteTransfer
0x1400014c3  nop     dword ptr [rax+rax+00h]
0x1400014c8  add     rsp, 48h
0x1400014cc  retn
```
