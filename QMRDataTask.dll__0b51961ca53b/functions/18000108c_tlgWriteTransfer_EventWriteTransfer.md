# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000108c`
- end: `0x18000113f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004344`

## callees

- `0x180014310`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001127`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001127`

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
0x18000108c  sub     rsp, 58h
0x180001090  mov     rax, cs:__security_cookie
0x180001097  xor     rax, rsp
0x18000109a  mov     [rsp+58h+var_10], rax
0x18000109f  movzx   eax, byte ptr [rdx]
0x1800010a2  mov     r11, rcx
0x1800010a5  mov     r10, [rsp+58h+arg_28]
0x1800010ad  shl     eax, 18h
0x1800010b0  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x1800010b4  movzx   eax, word ptr [rdx+1]
0x1800010b8  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x1800010bc  mov     rax, [rdx+3]
0x1800010c0  add     rdx, 0Bh
0x1800010c4  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x1800010c9  mov     rax, [rcx+8]
0x1800010cd  mov     [r10], rax
0x1800010d0  mov     rax, [rcx+8]
0x1800010d4  mov     [rsp+58h+UserData], r10; UserData
0x1800010d9  movzx   ecx, word ptr [rax]
0x1800010dc  mov     [r10+8], ecx
0x1800010e0  lea     rcx, _TraceLoggingMetadata
0x1800010e7  mov     [r10+10h], rdx
0x1800010eb  mov     dword ptr [r10+0Ch], 2
0x1800010f3  movzx   eax, word ptr [rdx]
0x1800010f6  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x1800010fb  mov     [r10+18h], eax
0x1800010ff  lea     rax, _TraceLoggingMetadataEnd
0x180001106  sub     eax, ecx
0x180001108  mov     dword ptr [r10+1Ch], 1
0x180001110  mov     [rsp+58h+var_28], eax
0x180001114  mov     eax, [rsp+58h+var_28]
0x180001118  mov     eax, [rsp+58h+arg_20]
0x18000111f  mov     rcx, [r11+20h]; RegHandle
0x180001123  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x180001127  call    cs:__imp_EventWriteTransfer
0x18000112d  mov     rcx, [rsp+58h+var_10]
0x180001132  xor     rcx, rsp; StackCookie
0x180001135  call    __security_check_cookie
0x18000113a  add     rsp, 58h
0x18000113e  retn
```
