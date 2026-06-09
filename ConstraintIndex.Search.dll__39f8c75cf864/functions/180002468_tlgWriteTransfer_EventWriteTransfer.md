# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180002468`
- end: `0x18000251b`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `23`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x1800012cc`
- `0x180001314`
- `0x180001628`
- `0x18000197c`
- `0x1800019ec`
- `0x180001a7c`
- `0x180001b78`
- `0x180001c38`
- `0x180001edc`
- `0x1800021d4`
- `0x180002524`
- `0x18000284c`
- `0x180002944`
- `0x180002c1c`
- `0x180002cf0`
- `0x180002db4`
- `0x1800030f8`
- `0x180003198`
- `0x18000325c`
- `0x1800035c8`
- `0x180003698`
- `0x1800891b8`

## callees

- `0x1800049e0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002503`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002503`

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
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-20h] BYREF

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
0x180002468  sub     rsp, 58h
0x18000246c  mov     rax, cs:__security_cookie
0x180002473  xor     rax, rsp
0x180002476  mov     [rsp+58h+var_10], rax
0x18000247b  movzx   eax, byte ptr [rdx]
0x18000247e  mov     r11, rcx
0x180002481  mov     r10, [rsp+58h+arg_28]
0x180002489  shl     eax, 18h
0x18000248c  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180002490  movzx   eax, word ptr [rdx+1]
0x180002494  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x180002498  mov     rax, [rdx+3]
0x18000249c  add     rdx, 0Bh
0x1800024a0  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x1800024a5  mov     rax, [rcx+8]
0x1800024a9  mov     [r10], rax
0x1800024ac  mov     rax, [rcx+8]
0x1800024b0  mov     [rsp+58h+UserData], r10; UserData
0x1800024b5  movzx   ecx, word ptr [rax]
0x1800024b8  mov     [r10+8], ecx
0x1800024bc  lea     rcx, _TraceLoggingMetadata
0x1800024c3  mov     [r10+10h], rdx
0x1800024c7  mov     dword ptr [r10+0Ch], 2
0x1800024cf  movzx   eax, word ptr [rdx]
0x1800024d2  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x1800024d7  mov     [r10+18h], eax
0x1800024db  lea     rax, _TraceLoggingMetadataEnd
0x1800024e2  sub     eax, ecx
0x1800024e4  mov     dword ptr [r10+1Ch], 1
0x1800024ec  mov     [rsp+58h+var_28], eax
0x1800024f0  mov     eax, [rsp+58h+var_28]
0x1800024f4  mov     eax, [rsp+58h+arg_20]
0x1800024fb  mov     rcx, [r11+20h]; RegHandle
0x1800024ff  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x180002503  call    cs:__imp_EventWriteTransfer
0x180002509  mov     rcx, [rsp+58h+var_10]
0x18000250e  xor     rcx, rsp; StackCookie
0x180002511  call    __security_check_cookie
0x180002516  add     rsp, 58h
0x18000251a  retn
```
