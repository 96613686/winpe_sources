# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001228`
- end: `0x1800012bf`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `21`
- callee_count: `0`
- tags: ``

## callers

- `0x1800010c0`
- `0x1800012c8`
- `0x1800013c4`
- `0x1800014bc`
- `0x180001584`
- `0x180001630`
- `0x1800016ac`
- `0x180001744`
- `0x180001900`
- `0x1800019c8`
- `0x180001a44`
- `0x180001aa8`
- `0x180001b18`
- `0x180001ba8`
- `0x180001c78`
- `0x180001d38`
- `0x180001fec`
- `0x180002300`
- `0x1800023fc`
- `0x1800026a0`
- `0x18001a55c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800012b4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800012b4`

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
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

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
0x180001228  sub     rsp, 48h
0x18000122c  movzx   eax, byte ptr [rdx]
0x18000122f  mov     r11, rcx
0x180001232  shl     eax, 18h
0x180001235  mov     r10, r8
0x180001238  mov     r8, [rsp+48h+arg_28]
0x18000123d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001241  movzx   eax, word ptr [rdx+1]
0x180001245  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001249  mov     rax, [rdx+3]
0x18000124d  add     rdx, 0Bh
0x180001251  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001256  mov     rax, [rcx+8]
0x18000125a  mov     [r8], rax
0x18000125d  mov     rax, [rcx+8]
0x180001261  mov     [rsp+48h+UserData], r8; UserData
0x180001266  movzx   ecx, word ptr [rax]
0x180001269  mov     [r8+8], ecx
0x18000126d  lea     rcx, _TraceLoggingMetadata
0x180001274  mov     [r8+10h], rdx
0x180001278  mov     dword ptr [r8+0Ch], 2
0x180001280  movzx   eax, word ptr [rdx]
0x180001283  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001288  mov     [r8+18h], eax
0x18000128c  lea     rax, _TraceLoggingMetadataEnd
0x180001293  sub     eax, ecx
0x180001295  mov     dword ptr [r8+1Ch], 1
0x18000129d  mov     dword ptr [rsp+48h+arg_28], eax
0x1800012a1  mov     r8, r10; ActivityId
0x1800012a4  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800012a8  mov     eax, [rsp+48h+arg_20]
0x1800012ac  mov     rcx, [r11+20h]; RegHandle
0x1800012b0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800012b4  call    cs:__imp_EventWriteTransfer
0x1800012ba  add     rsp, 48h
0x1800012be  retn
```
