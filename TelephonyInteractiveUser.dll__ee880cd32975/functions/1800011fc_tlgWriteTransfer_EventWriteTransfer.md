# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800011fc`
- end: `0x1800012af`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x1800012b8`
- `0x180001348`
- `0x1800013f0`
- `0x18000155c`
- `0x1800016a4`
- `0x180001764`
- `0x180010990`
- `0x180011aa4`
- `0x180011ca0`
- `0x180012410`
- `0x1800127d8`
- `0x1800136d0`
- `0x180013ec0`
- `0x180014210`
- `0x180015020`
- `0x180015944`
- `0x180015a7c`
- `0x180015b3c`
- `0x180015cf4`
- `0x180015dc0`

## callees

- `0x180001dc0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001297`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001297`

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
0x1800011fc  sub     rsp, 58h
0x180001200  mov     rax, cs:__security_cookie
0x180001207  xor     rax, rsp
0x18000120a  mov     [rsp+58h+var_10], rax
0x18000120f  movzx   eax, byte ptr [rdx]
0x180001212  mov     r11, rcx
0x180001215  mov     r10, [rsp+58h+arg_28]
0x18000121d  shl     eax, 18h
0x180001220  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180001224  movzx   eax, word ptr [rdx+1]
0x180001228  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x18000122c  mov     rax, [rdx+3]
0x180001230  add     rdx, 0Bh
0x180001234  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x180001239  mov     rax, [rcx+8]
0x18000123d  mov     [r10], rax
0x180001240  mov     rax, [rcx+8]
0x180001244  mov     [rsp+58h+UserData], r10; UserData
0x180001249  movzx   ecx, word ptr [rax]
0x18000124c  mov     [r10+8], ecx
0x180001250  lea     rcx, _TraceLoggingMetadata
0x180001257  mov     [r10+10h], rdx
0x18000125b  mov     dword ptr [r10+0Ch], 2
0x180001263  movzx   eax, word ptr [rdx]
0x180001266  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x18000126b  mov     [r10+18h], eax
0x18000126f  lea     rax, _TraceLoggingMetadataEnd
0x180001276  sub     eax, ecx
0x180001278  mov     dword ptr [r10+1Ch], 1
0x180001280  mov     [rsp+58h+var_28], eax
0x180001284  mov     eax, [rsp+58h+var_28]
0x180001288  mov     eax, [rsp+58h+arg_20]
0x18000128f  mov     rcx, [r11+20h]; RegHandle
0x180001293  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x180001297  call    cs:__imp_EventWriteTransfer
0x18000129d  mov     rcx, [rsp+58h+var_10]
0x1800012a2  xor     rcx, rsp; StackCookie
0x1800012a5  call    __security_check_cookie
0x1800012aa  add     rsp, 58h
0x1800012ae  retn
```
