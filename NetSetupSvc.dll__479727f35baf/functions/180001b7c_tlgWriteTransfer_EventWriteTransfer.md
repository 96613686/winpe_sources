# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001b7c`
- end: `0x180001c2f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000116c`
- `0x180001420`
- `0x180001734`
- `0x1800017c4`
- `0x180001abc`
- `0x180001c38`
- `0x180001d2c`
- `0x180001dd8`
- `0x180011dac`
- `0x180021650`

## callees

- `0x1800027c0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001c17`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001c17`

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
0x180001b7c  sub     rsp, 58h
0x180001b80  mov     rax, cs:__security_cookie
0x180001b87  xor     rax, rsp
0x180001b8a  mov     [rsp+58h+var_10], rax
0x180001b8f  movzx   eax, byte ptr [rdx]
0x180001b92  mov     r11, rcx
0x180001b95  mov     r10, [rsp+58h+arg_28]
0x180001b9d  shl     eax, 18h
0x180001ba0  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180001ba4  movzx   eax, word ptr [rdx+1]
0x180001ba8  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x180001bac  mov     rax, [rdx+3]
0x180001bb0  add     rdx, 0Bh
0x180001bb4  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x180001bb9  mov     rax, [rcx+8]
0x180001bbd  mov     [r10], rax
0x180001bc0  mov     rax, [rcx+8]
0x180001bc4  mov     [rsp+58h+UserData], r10; UserData
0x180001bc9  movzx   ecx, word ptr [rax]
0x180001bcc  mov     [r10+8], ecx
0x180001bd0  lea     rcx, _TraceLoggingMetadata
0x180001bd7  mov     [r10+10h], rdx
0x180001bdb  mov     dword ptr [r10+0Ch], 2
0x180001be3  movzx   eax, word ptr [rdx]
0x180001be6  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x180001beb  mov     [r10+18h], eax
0x180001bef  lea     rax, _TraceLoggingMetadataEnd
0x180001bf6  sub     eax, ecx
0x180001bf8  mov     dword ptr [r10+1Ch], 1
0x180001c00  mov     [rsp+58h+var_28], eax
0x180001c04  mov     eax, [rsp+58h+var_28]
0x180001c08  mov     eax, [rsp+58h+arg_20]
0x180001c0f  mov     rcx, [r11+20h]; RegHandle
0x180001c13  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x180001c17  call    cs:__imp_EventWriteTransfer
0x180001c1d  mov     rcx, [rsp+58h+var_10]
0x180001c22  xor     rcx, rsp; StackCookie
0x180001c25  call    __security_check_cookie
0x180001c2a  add     rsp, 58h
0x180001c2e  retn
```
