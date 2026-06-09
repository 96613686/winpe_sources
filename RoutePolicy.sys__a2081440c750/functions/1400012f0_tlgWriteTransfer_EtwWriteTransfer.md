# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x1400012f0`
- end: `0x1400013aa`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `186`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `33`
- callee_count: `1`
- tags: ``

## callers

- `0x140001008`
- `0x1400010b0`
- `0x14000116c`
- `0x140001244`
- `0x1400013b0`
- `0x140001440`
- `0x140001bfc`
- `0x140001d94`
- `0x140002618`
- `0x1400037a4`
- `0x140003dac`
- `0x140003f18`
- `0x140004330`
- `0x140004800`
- `0x140004a84`
- `0x140004f20`
- `0x140005610`
- `0x140005874`
- `0x140005b60`
- `0x140005efc`
- `0x14000607c`
- `0x14000646c`
- `0x140006570`
- `0x14000664c`
- `0x140006afc`
- `0x140006cc4`
- `0x140006e28`
- `0x140007110`
- `0x140007280`
- `0x140008060`
- `0x1400081ec`
- `0x140009390`
- `0x14001903c`

## callees

- `0x14000a680`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000138b`
- `ntoskrnl!EtwWriteTransfer` at `0x14000138b`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteTransfer_EtwWriteTransfer(
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
  return EtwWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1400012f0  sub     rsp, 58h
0x1400012f4  mov     rax, cs:__security_cookie
0x1400012fb  xor     rax, rsp
0x1400012fe  mov     [rsp+58h+var_10], rax
0x140001303  movzx   eax, byte ptr [rdx]
0x140001306  mov     r11, rcx
0x140001309  mov     r10, [rsp+58h+arg_28]
0x140001311  shl     eax, 18h
0x140001314  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x140001318  movzx   eax, word ptr [rdx+1]
0x14000131c  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x140001320  mov     rax, [rdx+3]
0x140001324  add     rdx, 0Bh
0x140001328  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x14000132d  mov     rax, [rcx+8]
0x140001331  mov     [r10], rax
0x140001334  mov     rax, [rcx+8]
0x140001338  mov     [rsp+58h+UserData], r10; UserData
0x14000133d  movzx   ecx, word ptr [rax]
0x140001340  mov     [r10+8], ecx
0x140001344  lea     rcx, _TraceLoggingMetadata
0x14000134b  mov     [r10+10h], rdx
0x14000134f  mov     dword ptr [r10+0Ch], 2
0x140001357  movzx   eax, word ptr [rdx]
0x14000135a  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x14000135f  mov     [r10+18h], eax
0x140001363  lea     rax, _TraceLoggingMetadataEnd
0x14000136a  sub     eax, ecx
0x14000136c  mov     dword ptr [r10+1Ch], 1
0x140001374  mov     [rsp+58h+var_28], eax
0x140001378  mov     eax, [rsp+58h+var_28]
0x14000137c  mov     eax, [rsp+58h+arg_20]
0x140001383  mov     rcx, [r11+20h]; RegHandle
0x140001387  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x14000138b  call    cs:__imp_EtwWriteTransfer
0x140001392  nop     dword ptr [rax+rax+00h]
0x140001397  mov     rcx, [rsp+58h+var_10]
0x14000139c  xor     rcx, rsp; StackCookie
0x14000139f  call    __security_check_cookie
0x1400013a4  add     rsp, 58h
0x1400013a8  retn
```
