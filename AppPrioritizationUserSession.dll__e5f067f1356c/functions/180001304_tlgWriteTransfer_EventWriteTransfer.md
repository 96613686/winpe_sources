# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001304`
- end: `0x1800013b7`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x1800013c0`
- `0x1800077c0`
- `0x1800078a8`
- `0x180009110`
- `0x180009414`
- `0x180009a30`
- `0x180009f00`
- `0x18000a320`
- `0x18000a9d0`
- `0x18000ad10`

## callees

- `0x180002650`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000139f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000139f`

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
0x180001304  sub     rsp, 58h
0x180001308  mov     rax, cs:__security_cookie
0x18000130f  xor     rax, rsp
0x180001312  mov     [rsp+58h+var_10], rax
0x180001317  movzx   eax, byte ptr [rdx]
0x18000131a  mov     r11, rcx
0x18000131d  mov     r10, [rsp+58h+arg_28]
0x180001325  shl     eax, 18h
0x180001328  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x18000132c  movzx   eax, word ptr [rdx+1]
0x180001330  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x180001334  mov     rax, [rdx+3]
0x180001338  add     rdx, 0Bh
0x18000133c  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x180001341  mov     rax, [rcx+8]
0x180001345  mov     [r10], rax
0x180001348  mov     rax, [rcx+8]
0x18000134c  mov     [rsp+58h+UserData], r10; UserData
0x180001351  movzx   ecx, word ptr [rax]
0x180001354  mov     [r10+8], ecx
0x180001358  lea     rcx, _TraceLoggingMetadata
0x18000135f  mov     [r10+10h], rdx
0x180001363  mov     dword ptr [r10+0Ch], 2
0x18000136b  movzx   eax, word ptr [rdx]
0x18000136e  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x180001373  mov     [r10+18h], eax
0x180001377  lea     rax, _TraceLoggingMetadataEnd
0x18000137e  sub     eax, ecx
0x180001380  mov     dword ptr [r10+1Ch], 1
0x180001388  mov     [rsp+58h+var_28], eax
0x18000138c  mov     eax, [rsp+58h+var_28]
0x180001390  mov     eax, [rsp+58h+arg_20]
0x180001397  mov     rcx, [r11+20h]; RegHandle
0x18000139b  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x18000139f  call    cs:__imp_EventWriteTransfer
0x1800013a5  mov     rcx, [rsp+58h+var_10]
0x1800013aa  xor     rcx, rsp; StackCookie
0x1800013ad  call    __security_check_cookie
0x1800013b2  add     rsp, 58h
0x1800013b6  retn
```
