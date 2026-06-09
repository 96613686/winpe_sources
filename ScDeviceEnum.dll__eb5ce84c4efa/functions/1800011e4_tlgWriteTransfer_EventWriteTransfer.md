# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800011e4`
- end: `0x180001285`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `161`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, struct _EVENT_DATA_DESCRIPTOR *)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x18001317c`
- `0x1800135d0`
- `0x180013910`
- `0x180013ca8`
- `0x180016d74`
- `0x180017f9c`
- `0x180019250`
- `0x180019d6c`
- `0x18001a260`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000127a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000127a`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_EventWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
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
  a6->Ptr = (ULONGLONG)off_18002B010;
  a6->Size = (unsigned __int16)*off_18002B010;
  a6[1].Ptr = (ULONGLONG)v7;
  a6->Reserved = 2;
  a6[1].Size = *v7;
  a6[1].Reserved = 1;
  return EventWriteTransfer(RegHandle, &v9, a3, a4, UserDataCount, a6);
}

```

## disassembly

```asm
0x1800011e4  mov     r11, rsp
0x1800011e7  mov     [r11+8], rcx
0x1800011eb  sub     rsp, 48h
0x1800011ef  movzx   eax, byte ptr [rdx]
0x1800011f2  mov     r10, r9
0x1800011f5  mov     r9, [rsp+48h+arg_28]
0x1800011fa  shl     eax, 18h
0x1800011fd  mov     [rsp+48h+var_18], eax
0x180001201  movzx   eax, word ptr [rdx+1]
0x180001205  mov     [rsp+48h+var_14], eax
0x180001209  mov     rax, [rdx+3]
0x18000120d  add     rdx, 0Bh
0x180001211  mov     [r11-10h], rax
0x180001215  mov     rax, cs:off_18002B010
0x18000121c  mov     [r9], rax
0x18000121f  mov     rax, cs:off_18002B010
0x180001226  mov     [r11-20h], r9
0x18000122a  movzx   ecx, word ptr [rax]
0x18000122d  mov     [r9+8], ecx
0x180001231  lea     rcx, _TraceLoggingMetadata
0x180001238  mov     [r9+10h], rdx
0x18000123c  mov     dword ptr [r9+0Ch], 2
0x180001244  movzx   eax, word ptr [rdx]
0x180001247  lea     rdx, [r11-18h]; EventDescriptor
0x18000124b  mov     [r9+18h], eax
0x18000124f  lea     rax, _TraceLoggingMetadataEnd
0x180001256  sub     eax, ecx
0x180001258  mov     dword ptr [r9+1Ch], 1
0x180001260  mov     [rsp+48h+arg_0], eax
0x180001264  mov     r9, r10; RelatedActivityId
0x180001267  mov     eax, [rsp+48h+arg_0]
0x18000126b  mov     eax, [rsp+48h+arg_20]
0x18000126f  mov     rcx, cs:RegHandle; RegHandle
0x180001276  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000127a  call    cs:__imp_EventWriteTransfer
0x180001280  add     rsp, 48h
0x180001284  retn
```
