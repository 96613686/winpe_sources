# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001058`
- end: `0x18000110b`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `22`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180001114`
- `0x1800011f0`
- `0x1800014a4`
- `0x180001928`
- `0x1800019b8`
- `0x180001a30`
- `0x180001ac4`
- `0x180001b88`
- `0x180001be8`
- `0x180001c94`
- `0x180001db0`
- `0x180001e28`
- `0x180001ea0`
- `0x180001f34`
- `0x18000220c`
- `0x1800022e0`
- `0x18001d9c4`
- `0x18001da44`
- `0x18001dc80`
- `0x180038184`
- `0x1800385d0`

## callees

- `0x180002b20`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800010f3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800010f3`

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
0x180001058  sub     rsp, 58h
0x18000105c  mov     rax, cs:__security_cookie
0x180001063  xor     rax, rsp
0x180001066  mov     [rsp+58h+var_10], rax
0x18000106b  movzx   eax, byte ptr [rdx]
0x18000106e  mov     r11, rcx
0x180001071  mov     r10, [rsp+58h+arg_28]
0x180001079  shl     eax, 18h
0x18000107c  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180001080  movzx   eax, word ptr [rdx+1]
0x180001084  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x180001088  mov     rax, [rdx+3]
0x18000108c  add     rdx, 0Bh
0x180001090  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x180001095  mov     rax, [rcx+8]
0x180001099  mov     [r10], rax
0x18000109c  mov     rax, [rcx+8]
0x1800010a0  mov     [rsp+58h+UserData], r10; UserData
0x1800010a5  movzx   ecx, word ptr [rax]
0x1800010a8  mov     [r10+8], ecx
0x1800010ac  lea     rcx, _TraceLoggingMetadata
0x1800010b3  mov     [r10+10h], rdx
0x1800010b7  mov     dword ptr [r10+0Ch], 2
0x1800010bf  movzx   eax, word ptr [rdx]
0x1800010c2  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x1800010c7  mov     [r10+18h], eax
0x1800010cb  lea     rax, _TraceLoggingMetadataEnd
0x1800010d2  sub     eax, ecx
0x1800010d4  mov     dword ptr [r10+1Ch], 1
0x1800010dc  mov     [rsp+58h+var_28], eax
0x1800010e0  mov     eax, [rsp+58h+var_28]
0x1800010e4  mov     eax, [rsp+58h+arg_20]
0x1800010eb  mov     rcx, [r11+20h]; RegHandle
0x1800010ef  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x1800010f3  call    cs:__imp_EventWriteTransfer
0x1800010f9  mov     rcx, [rsp+58h+var_10]
0x1800010fe  xor     rcx, rsp; StackCookie
0x180001101  call    __security_check_cookie
0x180001106  add     rsp, 58h
0x18000110a  retn
```
