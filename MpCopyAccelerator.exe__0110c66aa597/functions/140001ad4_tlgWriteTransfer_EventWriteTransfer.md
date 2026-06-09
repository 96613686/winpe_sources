# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001ad4`
- end: `0x140001b87`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400010ac`
- `0x140001440`
- `0x140001724`

## callees

- `0x140005c20`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x140001b6f`
- `ADVAPI32!EventWriteTransfer` at `0x140001b6f`

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
0x140001ad4  sub     rsp, 58h
0x140001ad8  mov     rax, cs:__security_cookie
0x140001adf  xor     rax, rsp
0x140001ae2  mov     [rsp+58h+var_10], rax
0x140001ae7  movzx   eax, byte ptr [rdx]
0x140001aea  mov     r11, rcx
0x140001aed  mov     r10, [rsp+58h+arg_28]
0x140001af5  shl     eax, 18h
0x140001af8  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x140001afc  movzx   eax, word ptr [rdx+1]
0x140001b00  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x140001b04  mov     rax, [rdx+3]
0x140001b08  add     rdx, 0Bh
0x140001b0c  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x140001b11  mov     rax, [rcx+8]
0x140001b15  mov     [r10], rax
0x140001b18  mov     rax, [rcx+8]
0x140001b1c  mov     [rsp+58h+UserData], r10; UserData
0x140001b21  movzx   ecx, word ptr [rax]
0x140001b24  mov     [r10+8], ecx
0x140001b28  lea     rcx, _TraceLoggingMetadata
0x140001b2f  mov     [r10+10h], rdx
0x140001b33  mov     dword ptr [r10+0Ch], 2
0x140001b3b  movzx   eax, word ptr [rdx]
0x140001b3e  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x140001b43  mov     [r10+18h], eax
0x140001b47  lea     rax, _TraceLoggingMetadataEnd
0x140001b4e  sub     eax, ecx
0x140001b50  mov     dword ptr [r10+1Ch], 1
0x140001b58  mov     [rsp+58h+var_28], eax
0x140001b5c  mov     eax, [rsp+58h+var_28]
0x140001b60  mov     eax, [rsp+58h+arg_20]
0x140001b67  mov     rcx, [r11+20h]; RegHandle
0x140001b6b  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x140001b6f  call    cs:__imp_EventWriteTransfer
0x140001b75  mov     rcx, [rsp+58h+var_10]
0x140001b7a  xor     rcx, rsp; StackCookie
0x140001b7d  call    __security_check_cookie
0x140001b82  add     rsp, 58h
0x140001b86  retn
```
