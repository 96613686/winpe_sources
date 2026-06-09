# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800020dc`
- end: `0x18000218f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x1800012e0`
- `0x1800013a4`
- `0x180001658`
- `0x18000196c`
- `0x1800019fc`
- `0x180001ca0`
- `0x180001f98`
- `0x18000fac8`
- `0x180016320`
- `0x180024764`

## callees

- `0x180003520`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002177`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002177`

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
0x1800020dc  sub     rsp, 58h
0x1800020e0  mov     rax, cs:__security_cookie
0x1800020e7  xor     rax, rsp
0x1800020ea  mov     [rsp+58h+var_10], rax
0x1800020ef  movzx   eax, byte ptr [rdx]
0x1800020f2  mov     r11, rcx
0x1800020f5  mov     r10, [rsp+58h+arg_28]
0x1800020fd  shl     eax, 18h
0x180002100  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180002104  movzx   eax, word ptr [rdx+1]
0x180002108  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x18000210c  mov     rax, [rdx+3]
0x180002110  add     rdx, 0Bh
0x180002114  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x180002119  mov     rax, [rcx+8]
0x18000211d  mov     [r10], rax
0x180002120  mov     rax, [rcx+8]
0x180002124  mov     [rsp+58h+UserData], r10; UserData
0x180002129  movzx   ecx, word ptr [rax]
0x18000212c  mov     [r10+8], ecx
0x180002130  lea     rcx, _TraceLoggingMetadata
0x180002137  mov     [r10+10h], rdx
0x18000213b  mov     dword ptr [r10+0Ch], 2
0x180002143  movzx   eax, word ptr [rdx]
0x180002146  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x18000214b  mov     [r10+18h], eax
0x18000214f  lea     rax, _TraceLoggingMetadataEnd
0x180002156  sub     eax, ecx
0x180002158  mov     dword ptr [r10+1Ch], 1
0x180002160  mov     [rsp+58h+var_28], eax
0x180002164  mov     eax, [rsp+58h+var_28]
0x180002168  mov     eax, [rsp+58h+arg_20]
0x18000216f  mov     rcx, [r11+20h]; RegHandle
0x180002173  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x180002177  call    cs:__imp_EventWriteTransfer
0x18000217d  mov     rcx, [rsp+58h+var_10]
0x180002182  xor     rcx, rsp; StackCookie
0x180002185  call    __security_check_cookie
0x18000218a  add     rsp, 58h
0x18000218e  retn
```
