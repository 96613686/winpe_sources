# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001008`
- end: `0x1800010bb`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800010c4`
- `0x18000d4c0`
- `0x18000d750`
- `0x18000d938`
- `0x18000dc90`
- `0x18000de04`
- `0x18000e804`
- `0x18000ece8`
- `0x18000ef58`

## callees

- `0x1800107c0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800010a3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800010a3`

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
0x180001008  sub     rsp, 58h
0x18000100c  mov     rax, cs:__security_cookie
0x180001013  xor     rax, rsp
0x180001016  mov     [rsp+58h+var_10], rax
0x18000101b  movzx   eax, byte ptr [rdx]
0x18000101e  mov     r11, rcx
0x180001021  mov     r10, [rsp+58h+arg_28]
0x180001029  shl     eax, 18h
0x18000102c  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180001030  movzx   eax, word ptr [rdx+1]
0x180001034  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x180001038  mov     rax, [rdx+3]
0x18000103c  add     rdx, 0Bh
0x180001040  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x180001045  mov     rax, [rcx+8]
0x180001049  mov     [r10], rax
0x18000104c  mov     rax, [rcx+8]
0x180001050  mov     [rsp+58h+UserData], r10; UserData
0x180001055  movzx   ecx, word ptr [rax]
0x180001058  mov     [r10+8], ecx
0x18000105c  lea     rcx, _TraceLoggingMetadata
0x180001063  mov     [r10+10h], rdx
0x180001067  mov     dword ptr [r10+0Ch], 2
0x18000106f  movzx   eax, word ptr [rdx]
0x180001072  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x180001077  mov     [r10+18h], eax
0x18000107b  lea     rax, _TraceLoggingMetadataEnd
0x180001082  sub     eax, ecx
0x180001084  mov     dword ptr [r10+1Ch], 1
0x18000108c  mov     [rsp+58h+var_28], eax
0x180001090  mov     eax, [rsp+58h+var_28]
0x180001094  mov     eax, [rsp+58h+arg_20]
0x18000109b  mov     rcx, [r11+20h]; RegHandle
0x18000109f  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x1800010a3  call    cs:__imp_EventWriteTransfer
0x1800010a9  mov     rcx, [rsp+58h+var_10]
0x1800010ae  xor     rcx, rsp; StackCookie
0x1800010b1  call    __security_check_cookie
0x1800010b6  add     rsp, 58h
0x1800010ba  retn
```
