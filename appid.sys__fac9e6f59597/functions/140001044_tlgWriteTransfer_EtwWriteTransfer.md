# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001044`
- end: `0x1400010ec`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `168`
- prototype: `NTSTATUS __fastcall(__int64, unsigned __int8 *, __int64, __int64, ULONG UserDataCount, struct _EVENT_DATA_DESCRIPTOR *)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140021d30`
- `0x140022c20`
- `0x140025560`
- `0x14002b5e0`
- `0x14002daa0`
- `0x14002dbbc`
- `0x14003825c`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400010da`
- `ntoskrnl!EtwWriteTransfer` at `0x1400010da`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteTransfer_EtwWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        ULONG UserDataCount,
        struct _EVENT_DATA_DESCRIPTOR *a6)
{
  ULONGLONG v6; // rax
  unsigned __int16 *v7; // rdx
  EVENT_DESCRIPTOR v9; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&v9.Id = *a2 << 24;
  *(_DWORD *)&v9.Level = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = (unsigned __int16 *)(a2 + 11);
  v9.Keyword = v6;
  a6->Ptr = (ULONGLONG)EventInformation;
  a6->Size = *(unsigned __int16 *)EventInformation;
  a6[1].Ptr = (ULONGLONG)v7;
  a6->Reserved = 2;
  a6[1].Size = *v7;
  a6[1].Reserved = 1;
  return EtwWriteTransfer(RegHandle, &v9, 0, 0, UserDataCount, a6);
}

```

## disassembly

```asm
0x140001044  mov     r11, rsp
0x140001047  mov     [r11+20h], r9
0x14000104b  sub     rsp, 48h
0x14000104f  movzx   eax, byte ptr [rdx]
0x140001052  xor     r9d, r9d; RelatedActivityId
0x140001055  mov     r8, [rsp+48h+arg_28]
0x14000105a  shl     eax, 18h
0x14000105d  mov     [rsp+48h+var_18], eax
0x140001061  movzx   eax, word ptr [rdx+1]
0x140001065  mov     [rsp+48h+var_14], eax
0x140001069  mov     rax, [rdx+3]
0x14000106d  add     rdx, 0Bh
0x140001071  mov     [r11-10h], rax
0x140001075  mov     rax, cs:EventInformation
0x14000107c  mov     [r8], rax
0x14000107f  mov     rax, cs:EventInformation
0x140001086  mov     [r11-20h], r8
0x14000108a  movzx   ecx, word ptr [rax]
0x14000108d  mov     [r8+8], ecx
0x140001091  lea     rcx, _TraceLoggingMetadata
0x140001098  mov     [r8+10h], rdx
0x14000109c  mov     dword ptr [r8+0Ch], 2
0x1400010a4  movzx   eax, word ptr [rdx]
0x1400010a7  lea     rdx, [r11-18h]; EventDescriptor
0x1400010ab  mov     [r8+18h], eax
0x1400010af  lea     rax, _TraceLoggingMetadataEnd
0x1400010b6  sub     eax, ecx
0x1400010b8  mov     dword ptr [r8+1Ch], 1
0x1400010c0  mov     [rsp+48h+arg_18], eax
0x1400010c4  xor     r8d, r8d; ActivityId
0x1400010c7  mov     eax, [rsp+48h+arg_18]
0x1400010cb  mov     eax, [rsp+48h+arg_20]
0x1400010cf  mov     rcx, cs:RegHandle; RegHandle
0x1400010d6  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400010da  call    cs:__imp_EtwWriteTransfer
0x1400010e1  nop     dword ptr [rax+rax+00h]
0x1400010e6  add     rsp, 48h
0x1400010ea  retn
```
