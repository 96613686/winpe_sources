# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180019b1c`
- end: `0x180019bcf`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x1800010c8`
- `0x1800011c0`
- `0x180019a70`

## callees

- `0x18001f650`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019bb7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019bb7`

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
0x180019b1c  sub     rsp, 58h
0x180019b20  mov     rax, cs:__security_cookie
0x180019b27  xor     rax, rsp
0x180019b2a  mov     [rsp+58h+var_10], rax
0x180019b2f  movzx   eax, byte ptr [rdx]
0x180019b32  mov     r11, rcx
0x180019b35  mov     r10, [rsp+58h+arg_28]
0x180019b3d  shl     eax, 18h
0x180019b40  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180019b44  movzx   eax, word ptr [rdx+1]
0x180019b48  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x180019b4c  mov     rax, [rdx+3]
0x180019b50  add     rdx, 0Bh
0x180019b54  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x180019b59  mov     rax, [rcx+8]
0x180019b5d  mov     [r10], rax
0x180019b60  mov     rax, [rcx+8]
0x180019b64  mov     [rsp+58h+UserData], r10; UserData
0x180019b69  movzx   ecx, word ptr [rax]
0x180019b6c  mov     [r10+8], ecx
0x180019b70  lea     rcx, _TraceLoggingMetadata
0x180019b77  mov     [r10+10h], rdx
0x180019b7b  mov     dword ptr [r10+0Ch], 2
0x180019b83  movzx   eax, word ptr [rdx]
0x180019b86  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x180019b8b  mov     [r10+18h], eax
0x180019b8f  lea     rax, _TraceLoggingMetadataEnd
0x180019b96  sub     eax, ecx
0x180019b98  mov     dword ptr [r10+1Ch], 1
0x180019ba0  mov     [rsp+58h+var_28], eax
0x180019ba4  mov     eax, [rsp+58h+var_28]
0x180019ba8  mov     eax, [rsp+58h+arg_20]
0x180019baf  mov     rcx, [r11+20h]; RegHandle
0x180019bb3  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x180019bb7  call    cs:__imp_EventWriteTransfer
0x180019bbd  mov     rcx, [rsp+58h+var_10]
0x180019bc2  xor     rcx, rsp; StackCookie
0x180019bc5  call    __security_check_cookie
0x180019bca  add     rsp, 58h
0x180019bce  retn
```
