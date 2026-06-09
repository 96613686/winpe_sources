# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800013b4`
- end: `0x180001467`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `42`
- callee_count: `1`
- tags: ``

## callers

- `0x18000119c`
- `0x18000128c`
- `0x180001470`
- `0x180001858`
- `0x1800018ec`
- `0x180001ba0`
- `0x180001eb4`
- `0x1800021b0`
- `0x180002550`
- `0x180002864`
- `0x180002910`
- `0x1800029d8`
- `0x180002a68`
- `0x180002b64`
- `0x180002c44`
- `0x180002ee8`
- `0x18001d53c`
- `0x18001d758`
- `0x18001d868`
- `0x18001dba0`
- `0x18001dd04`
- `0x18001e068`
- `0x18001e228`
- `0x18001e330`
- `0x18001e448`
- `0x18001e534`
- `0x18001e6c8`
- `0x180025a78`
- `0x180025ad0`
- `0x1800280b0`
- `0x180028998`
- `0x1800292fc`
- `0x1800294ac`
- `0x1800295dc`
- `0x1800296f4`
- `0x18002a2e4`
- `0x18002a440`
- `0x18002a648`
- `0x18002a7a4`
- `0x18002a924`
- `0x18002afa8`
- `0x18002b4e4`

## callees

- `0x180003870`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000144f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000144f`

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
0x1800013b4  sub     rsp, 58h
0x1800013b8  mov     rax, cs:__security_cookie
0x1800013bf  xor     rax, rsp
0x1800013c2  mov     [rsp+58h+var_10], rax
0x1800013c7  movzx   eax, byte ptr [rdx]
0x1800013ca  mov     r11, rcx
0x1800013cd  mov     r10, [rsp+58h+arg_28]
0x1800013d5  shl     eax, 18h
0x1800013d8  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x1800013dc  movzx   eax, word ptr [rdx+1]
0x1800013e0  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x1800013e4  mov     rax, [rdx+3]
0x1800013e8  add     rdx, 0Bh
0x1800013ec  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x1800013f1  mov     rax, [rcx+8]
0x1800013f5  mov     [r10], rax
0x1800013f8  mov     rax, [rcx+8]
0x1800013fc  mov     [rsp+58h+UserData], r10; UserData
0x180001401  movzx   ecx, word ptr [rax]
0x180001404  mov     [r10+8], ecx
0x180001408  lea     rcx, _TraceLoggingMetadata
0x18000140f  mov     [r10+10h], rdx
0x180001413  mov     dword ptr [r10+0Ch], 2
0x18000141b  movzx   eax, word ptr [rdx]
0x18000141e  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x180001423  mov     [r10+18h], eax
0x180001427  lea     rax, _TraceLoggingMetadataEnd
0x18000142e  sub     eax, ecx
0x180001430  mov     dword ptr [r10+1Ch], 1
0x180001438  mov     [rsp+58h+var_28], eax
0x18000143c  mov     eax, [rsp+58h+var_28]
0x180001440  mov     eax, [rsp+58h+arg_20]
0x180001447  mov     rcx, [r11+20h]; RegHandle
0x18000144b  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x18000144f  call    cs:__imp_EventWriteTransfer
0x180001455  mov     rcx, [rsp+58h+var_10]
0x18000145a  xor     rcx, rsp; StackCookie
0x18000145d  call    __security_check_cookie
0x180001462  add     rsp, 58h
0x180001466  retn
```
