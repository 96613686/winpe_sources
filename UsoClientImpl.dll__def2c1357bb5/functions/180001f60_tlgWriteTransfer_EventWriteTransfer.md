# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001f60`
- end: `0x180002013`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x1800013a4`
- `0x18000175c`
- `0x180001804`
- `0x1800018e0`
- `0x180001c1c`
- `0x180001cac`
- `0x18000201c`
- `0x180002314`
- `0x180002648`
- `0x18000a844`
- `0x18000aa8c`
- `0x18000af08`
- `0x18000b678`
- `0x18000ba08`
- `0x18000bbd0`
- `0x1800194f8`
- `0x180019694`
- `0x18003e568`
- `0x18003e700`
- `0x18003ea9c`

## callees

- `0x180056500`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001ffb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001ffb`

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
0x180001f60  sub     rsp, 58h
0x180001f64  mov     rax, cs:__security_cookie
0x180001f6b  xor     rax, rsp
0x180001f6e  mov     [rsp+58h+var_10], rax
0x180001f73  movzx   eax, byte ptr [rdx]
0x180001f76  mov     r11, rcx
0x180001f79  mov     r10, [rsp+58h+arg_28]
0x180001f81  shl     eax, 18h
0x180001f84  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180001f88  movzx   eax, word ptr [rdx+1]
0x180001f8c  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x180001f90  mov     rax, [rdx+3]
0x180001f94  add     rdx, 0Bh
0x180001f98  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x180001f9d  mov     rax, [rcx+8]
0x180001fa1  mov     [r10], rax
0x180001fa4  mov     rax, [rcx+8]
0x180001fa8  mov     [rsp+58h+UserData], r10; UserData
0x180001fad  movzx   ecx, word ptr [rax]
0x180001fb0  mov     [r10+8], ecx
0x180001fb4  lea     rcx, _TraceLoggingMetadata
0x180001fbb  mov     [r10+10h], rdx
0x180001fbf  mov     dword ptr [r10+0Ch], 2
0x180001fc7  movzx   eax, word ptr [rdx]
0x180001fca  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x180001fcf  mov     [r10+18h], eax
0x180001fd3  lea     rax, _TraceLoggingMetadataEnd
0x180001fda  sub     eax, ecx
0x180001fdc  mov     dword ptr [r10+1Ch], 1
0x180001fe4  mov     [rsp+58h+var_28], eax
0x180001fe8  mov     eax, [rsp+58h+var_28]
0x180001fec  mov     eax, [rsp+58h+arg_20]
0x180001ff3  mov     rcx, [r11+20h]; RegHandle
0x180001ff7  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x180001ffb  call    cs:__imp_EventWriteTransfer
0x180002001  mov     rcx, [rsp+58h+var_10]
0x180002006  xor     rcx, rsp; StackCookie
0x180002009  call    __security_check_cookie
0x18000200e  add     rsp, 58h
0x180002012  retn
```
