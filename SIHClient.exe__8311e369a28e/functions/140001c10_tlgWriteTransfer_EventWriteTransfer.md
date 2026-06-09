# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001c10`
- end: `0x140001cc3`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x140001008`
- `0x1400011b8`
- `0x1400013ec`
- `0x1400015b0`
- `0x1400017f0`
- `0x140001a48`
- `0x140001e18`
- `0x140001ea8`
- `0x14000c010`
- `0x1400375dc`
- `0x140037798`
- `0x140037a14`
- `0x140037ca8`
- `0x140037e58`
- `0x140038140`
- `0x140045050`

## callees

- `0x140045dc0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001cab`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001cab`

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
0x140001c10  sub     rsp, 58h
0x140001c14  mov     rax, cs:__security_cookie
0x140001c1b  xor     rax, rsp
0x140001c1e  mov     [rsp+58h+var_10], rax
0x140001c23  movzx   eax, byte ptr [rdx]
0x140001c26  mov     r11, rcx
0x140001c29  mov     r10, [rsp+58h+arg_28]
0x140001c31  shl     eax, 18h
0x140001c34  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x140001c38  movzx   eax, word ptr [rdx+1]
0x140001c3c  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x140001c40  mov     rax, [rdx+3]
0x140001c44  add     rdx, 0Bh
0x140001c48  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x140001c4d  mov     rax, [rcx+8]
0x140001c51  mov     [r10], rax
0x140001c54  mov     rax, [rcx+8]
0x140001c58  mov     [rsp+58h+UserData], r10; UserData
0x140001c5d  movzx   ecx, word ptr [rax]
0x140001c60  mov     [r10+8], ecx
0x140001c64  lea     rcx, _TraceLoggingMetadata
0x140001c6b  mov     [r10+10h], rdx
0x140001c6f  mov     dword ptr [r10+0Ch], 2
0x140001c77  movzx   eax, word ptr [rdx]
0x140001c7a  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x140001c7f  mov     [r10+18h], eax
0x140001c83  lea     rax, _TraceLoggingMetadataEnd
0x140001c8a  sub     eax, ecx
0x140001c8c  mov     dword ptr [r10+1Ch], 1
0x140001c94  mov     [rsp+58h+var_28], eax
0x140001c98  mov     eax, [rsp+58h+var_28]
0x140001c9c  mov     eax, [rsp+58h+arg_20]
0x140001ca3  mov     rcx, [r11+20h]; RegHandle
0x140001ca7  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x140001cab  call    cs:__imp_EventWriteTransfer
0x140001cb1  mov     rcx, [rsp+58h+var_10]
0x140001cb6  xor     rcx, rsp; StackCookie
0x140001cb9  call    __security_check_cookie
0x140001cbe  add     rsp, 58h
0x140001cc2  retn
```
