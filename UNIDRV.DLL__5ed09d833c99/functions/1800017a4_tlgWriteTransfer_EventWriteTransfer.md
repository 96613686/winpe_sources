# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800017a4`
- end: `0x180001842`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x1800010f0`
- `0x1800011c8`
- `0x18000147c`
- `0x180071ecc`
- `0x180071f54`
- `0x180071fdc`
- `0x180074fe8`
- `0x180075070`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180001830`
- `ADVAPI32!EventWriteTransfer` at `0x180001830`

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
  unsigned __int8 *v7; // rdx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = a2 + 11;
  EventDescriptor.Keyword = v6;
  UserData->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData->Reserved = 2;
  UserData[1].Size = *(unsigned __int16 *)v7;
  UserData[1].Reserved = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800017a4  sub     rsp, 48h
0x1800017a8  movzx   eax, byte ptr [rdx]
0x1800017ab  mov     r11, rcx
0x1800017ae  shl     eax, 18h
0x1800017b1  mov     r10, r8
0x1800017b4  mov     r8, [rsp+48h+arg_28]
0x1800017b9  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800017bd  movzx   eax, word ptr [rdx+1]
0x1800017c1  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800017c5  mov     rax, [rdx+3]
0x1800017c9  add     rdx, 0Bh
0x1800017cd  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800017d2  mov     rax, [rcx+8]
0x1800017d6  mov     [r8], rax
0x1800017d9  mov     rax, [rcx+8]
0x1800017dd  mov     [rsp+48h+UserData], r8; UserData
0x1800017e2  movzx   ecx, word ptr [rax]
0x1800017e5  mov     [r8+8], ecx
0x1800017e9  lea     rcx, _TraceLoggingMetadata
0x1800017f0  mov     [r8+10h], rdx
0x1800017f4  mov     dword ptr [r8+0Ch], 2
0x1800017fc  movzx   eax, word ptr [rdx]
0x1800017ff  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001804  mov     [r8+18h], eax
0x180001808  lea     rax, _TraceLoggingMetadataEnd
0x18000180f  sub     eax, ecx
0x180001811  mov     dword ptr [r8+1Ch], 1
0x180001819  mov     dword ptr [rsp+48h+arg_28], eax
0x18000181d  mov     r8, r10; ActivityId
0x180001820  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001824  mov     eax, [rsp+48h+arg_20]
0x180001828  mov     rcx, [r11+20h]; RegHandle
0x18000182c  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001830  call    cs:__imp_EventWriteTransfer
0x180001837  nop     dword ptr [rax+rax+00h]
0x18000183c  add     rsp, 48h
0x180001840  retn
```
