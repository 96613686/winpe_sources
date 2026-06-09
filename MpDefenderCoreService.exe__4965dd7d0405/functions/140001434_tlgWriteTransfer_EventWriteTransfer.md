# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001434`
- end: `0x1400014e7`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `31`
- callee_count: `1`
- tags: ``

## callers

- `0x1400010ac`
- `0x140001374`
- `0x1400014e8`
- `0x14000175c`
- `0x1400019d0`
- `0x140001c98`
- `0x140001f80`
- `0x1400022a8`
- `0x14000250c`
- `0x1400027c4`
- `0x1400029a4`
- `0x140002bc4`
- `0x140002e84`
- `0x140003070`
- `0x140003340`
- `0x1400033c8`
- `0x140003468`
- `0x140003520`
- `0x1400b09d0`
- `0x1400b4a6c`
- `0x1400c2874`
- `0x1400c5538`
- `0x1400e994c`
- `0x1400e99dc`
- `0x1400ea340`
- `0x1400eaa58`
- `0x1400ec350`
- `0x1400ed28c`
- `0x1400f0a80`
- `0x1400f1a48`
- `0x1400f2344`

## callees

- `0x14003a5c0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x1400014cf`
- `ADVAPI32!EventWriteTransfer` at `0x1400014cf`

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
0x140001434  sub     rsp, 58h
0x140001438  mov     rax, cs:__security_cookie
0x14000143f  xor     rax, rsp
0x140001442  mov     [rsp+58h+var_10], rax
0x140001447  movzx   eax, byte ptr [rdx]
0x14000144a  mov     r11, rcx
0x14000144d  mov     r10, [rsp+58h+arg_28]
0x140001455  shl     eax, 18h
0x140001458  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x14000145c  movzx   eax, word ptr [rdx+1]
0x140001460  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x140001464  mov     rax, [rdx+3]
0x140001468  add     rdx, 0Bh
0x14000146c  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x140001471  mov     rax, [rcx+8]
0x140001475  mov     [r10], rax
0x140001478  mov     rax, [rcx+8]
0x14000147c  mov     [rsp+58h+UserData], r10; UserData
0x140001481  movzx   ecx, word ptr [rax]
0x140001484  mov     [r10+8], ecx
0x140001488  lea     rcx, _TraceLoggingMetadata
0x14000148f  mov     [r10+10h], rdx
0x140001493  mov     dword ptr [r10+0Ch], 2
0x14000149b  movzx   eax, word ptr [rdx]
0x14000149e  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x1400014a3  mov     [r10+18h], eax
0x1400014a7  lea     rax, _TraceLoggingMetadataEnd
0x1400014ae  sub     eax, ecx
0x1400014b0  mov     dword ptr [r10+1Ch], 1
0x1400014b8  mov     [rsp+58h+var_28], eax
0x1400014bc  mov     eax, [rsp+58h+var_28]
0x1400014c0  mov     eax, [rsp+58h+arg_20]
0x1400014c7  mov     rcx, [r11+20h]; RegHandle
0x1400014cb  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x1400014cf  call    cs:__imp_EventWriteTransfer
0x1400014d5  mov     rcx, [rsp+58h+var_10]
0x1400014da  xor     rcx, rsp; StackCookie
0x1400014dd  call    __security_check_cookie
0x1400014e2  add     rsp, 58h
0x1400014e6  retn
```
