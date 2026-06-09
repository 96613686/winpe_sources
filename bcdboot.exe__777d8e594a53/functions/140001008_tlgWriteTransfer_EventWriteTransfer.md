# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001008`
- end: `0x1400010a3`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `155`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, ULONG UserDataCount, struct _EVENT_DATA_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140009658`
- `0x140009fd4`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x140001098`
- `ADVAPI32!EventWriteTransfer` at `0x140001098`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_EventWriteTransfer(
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
  a6->Ptr = *(_QWORD *)(a1 + 8);
  a6->Size = **(unsigned __int16 **)(a1 + 8);
  a6[1].Ptr = (ULONGLONG)v7;
  a6->Reserved = 2;
  a6[1].Size = *v7;
  a6[1].Reserved = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &v9, 0, 0, UserDataCount, a6);
}

```

## disassembly

```asm
0x140001008  mov     r11, rsp
0x14000100b  mov     [r11+20h], r9
0x14000100f  sub     rsp, 48h
0x140001013  movzx   eax, byte ptr [rdx]
0x140001016  mov     r10, rcx
0x140001019  mov     r8, [rsp+48h+arg_28]
0x14000101e  xor     r9d, r9d; RelatedActivityId
0x140001021  shl     eax, 18h
0x140001024  mov     [rsp+48h+var_18], eax
0x140001028  movzx   eax, word ptr [rdx+1]
0x14000102c  mov     [rsp+48h+var_14], eax
0x140001030  mov     rax, [rdx+3]
0x140001034  add     rdx, 0Bh
0x140001038  mov     [r11-10h], rax
0x14000103c  mov     rax, [rcx+8]
0x140001040  mov     [r8], rax
0x140001043  mov     rax, [rcx+8]
0x140001047  mov     [r11-20h], r8
0x14000104b  movzx   ecx, word ptr [rax]
0x14000104e  mov     [r8+8], ecx
0x140001052  lea     rcx, _TraceLoggingMetadata
0x140001059  mov     [r8+10h], rdx
0x14000105d  mov     dword ptr [r8+0Ch], 2
0x140001065  movzx   eax, word ptr [rdx]
0x140001068  lea     rdx, [r11-18h]; EventDescriptor
0x14000106c  mov     [r8+18h], eax
0x140001070  lea     rax, _TraceLoggingMetadataEnd
0x140001077  sub     eax, ecx
0x140001079  mov     dword ptr [r8+1Ch], 1
0x140001081  mov     [rsp+48h+arg_18], eax
0x140001085  xor     r8d, r8d; ActivityId
0x140001088  mov     eax, [rsp+48h+arg_18]
0x14000108c  mov     eax, [rsp+48h+arg_20]
0x140001090  mov     rcx, [r10+20h]; RegHandle
0x140001094  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001098  call    cs:__imp_EventWriteTransfer
0x14000109e  add     rsp, 48h
0x1400010a2  retn
```
