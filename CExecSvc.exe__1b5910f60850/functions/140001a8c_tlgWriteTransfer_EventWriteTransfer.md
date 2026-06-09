# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001a8c`
- end: `0x140001b3f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x14000113c`
- `0x1400013f0`
- `0x140001704`
- `0x140001794`
- `0x1400153a0`
- `0x1400196a0`
- `0x1400197f4`
- `0x140019948`

## callees

- `0x140002310`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001b27`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001b27`

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
0x140001a8c  sub     rsp, 58h
0x140001a90  mov     rax, cs:__security_cookie
0x140001a97  xor     rax, rsp
0x140001a9a  mov     [rsp+58h+var_10], rax
0x140001a9f  movzx   eax, byte ptr [rdx]
0x140001aa2  mov     r11, rcx
0x140001aa5  mov     r10, [rsp+58h+arg_28]
0x140001aad  shl     eax, 18h
0x140001ab0  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x140001ab4  movzx   eax, word ptr [rdx+1]
0x140001ab8  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x140001abc  mov     rax, [rdx+3]
0x140001ac0  add     rdx, 0Bh
0x140001ac4  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x140001ac9  mov     rax, [rcx+8]
0x140001acd  mov     [r10], rax
0x140001ad0  mov     rax, [rcx+8]
0x140001ad4  mov     [rsp+58h+UserData], r10; UserData
0x140001ad9  movzx   ecx, word ptr [rax]
0x140001adc  mov     [r10+8], ecx
0x140001ae0  lea     rcx, _TraceLoggingMetadata
0x140001ae7  mov     [r10+10h], rdx
0x140001aeb  mov     dword ptr [r10+0Ch], 2
0x140001af3  movzx   eax, word ptr [rdx]
0x140001af6  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x140001afb  mov     [r10+18h], eax
0x140001aff  lea     rax, _TraceLoggingMetadataEnd
0x140001b06  sub     eax, ecx
0x140001b08  mov     dword ptr [r10+1Ch], 1
0x140001b10  mov     [rsp+58h+var_28], eax
0x140001b14  mov     eax, [rsp+58h+var_28]
0x140001b18  mov     eax, [rsp+58h+arg_20]
0x140001b1f  mov     rcx, [r11+20h]; RegHandle
0x140001b23  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x140001b27  call    cs:__imp_EventWriteTransfer
0x140001b2d  mov     rcx, [rsp+58h+var_10]
0x140001b32  xor     rcx, rsp; StackCookie
0x140001b35  call    __security_check_cookie
0x140001b3a  add     rsp, 58h
0x140001b3e  retn
```
