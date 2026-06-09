# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180004950`
- end: `0x180004a03`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x180001140`
- `0x1800012cc`
- `0x180001404`
- `0x18000154c`
- `0x180001670`
- `0x180001770`
- `0x180001880`
- `0x180001954`
- `0x180001a6c`
- `0x180001b94`
- `0x180001c7c`
- `0x180001d54`
- `0x180001e6c`
- `0x180001f30`
- `0x180002000`
- `0x1800020fc`
- `0x18000219c`

## callees

- `0x18000d2a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800049eb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800049eb`

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
0x180004950  sub     rsp, 58h
0x180004954  mov     rax, cs:__security_cookie
0x18000495b  xor     rax, rsp
0x18000495e  mov     [rsp+58h+var_10], rax
0x180004963  movzx   eax, byte ptr [rdx]
0x180004966  mov     r11, rcx
0x180004969  mov     r10, [rsp+58h+arg_28]
0x180004971  shl     eax, 18h
0x180004974  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180004978  movzx   eax, word ptr [rdx+1]
0x18000497c  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x180004980  mov     rax, [rdx+3]
0x180004984  add     rdx, 0Bh
0x180004988  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x18000498d  mov     rax, [rcx+8]
0x180004991  mov     [r10], rax
0x180004994  mov     rax, [rcx+8]
0x180004998  mov     [rsp+58h+UserData], r10; UserData
0x18000499d  movzx   ecx, word ptr [rax]
0x1800049a0  mov     [r10+8], ecx
0x1800049a4  lea     rcx, _TraceLoggingMetadata
0x1800049ab  mov     [r10+10h], rdx
0x1800049af  mov     dword ptr [r10+0Ch], 2
0x1800049b7  movzx   eax, word ptr [rdx]
0x1800049ba  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x1800049bf  mov     [r10+18h], eax
0x1800049c3  lea     rax, _TraceLoggingMetadataEnd
0x1800049ca  sub     eax, ecx
0x1800049cc  mov     dword ptr [r10+1Ch], 1
0x1800049d4  mov     [rsp+58h+var_28], eax
0x1800049d8  mov     eax, [rsp+58h+var_28]
0x1800049dc  mov     eax, [rsp+58h+arg_20]
0x1800049e3  mov     rcx, [r11+20h]; RegHandle
0x1800049e7  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x1800049eb  call    cs:__imp_EventWriteTransfer
0x1800049f1  mov     rcx, [rsp+58h+var_10]
0x1800049f6  xor     rcx, rsp; StackCookie
0x1800049f9  call    __security_check_cookie
0x1800049fe  add     rsp, 58h
0x180004a02  retn
```
