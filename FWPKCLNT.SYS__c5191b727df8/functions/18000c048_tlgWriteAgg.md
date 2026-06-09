# _tlgWriteAgg

- ea: `0x18000c048`
- end: `0x18000c122`
- name: `_tlgWriteAgg`
- size: `218`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a8bc`

## callees

- `0x1800098a8`
- `0x180009930`
- `0x18000c048`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x18000c10a`
- `ntoskrnl!EtwWriteTransfer` at `0x18000c10a`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  ULONGLONG v6; // rax
  unsigned __int16 *v7; // rdx
  NTSTATUS result; // eax
  char AggregateFieldTypes; // al
  int v10; // r8d
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v6;
  UserData->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData->Reserved = 2;
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData[1].Size = *v7;
  UserData[1].Reserved = 1;
  result = -1073741811;
  if ( *(void (__fastcall **)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))(a1 + 40) == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    AggregateFieldTypes = ExtractAggregateFieldTypes(TlgAggregateInternalRegisteredProviderEtwCallback, UserData);
    if ( AggregateFieldTypes )
      return InsertEventEntryInLookUpTable(
               a1,
               (unsigned int)&EventDescriptor,
               v10,
               (_DWORD)UserData,
               AggregateFieldTypes);
    else
      return EtwWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 5u, UserData);
  }
  return result;
}

```

## disassembly

```asm
0x18000c048  mov     [rsp+arg_0], rbx
0x18000c04d  mov     [rsp+arg_18], r9d
0x18000c052  push    rdi
0x18000c053  sub     rsp, 40h
0x18000c057  movzx   eax, byte ptr [rdx]
0x18000c05a  mov     rdi, rcx
0x18000c05d  mov     rbx, [rsp+48h+arg_20]
0x18000c062  shl     eax, 18h
0x18000c065  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000c069  movzx   eax, word ptr [rdx+1]
0x18000c06d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000c071  mov     rax, [rdx+3]
0x18000c075  add     rdx, 0Bh
0x18000c079  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000c07e  mov     rax, [rcx+8]
0x18000c082  mov     [rbx], rax
0x18000c085  mov     rax, [rcx+8]
0x18000c089  movzx   ecx, word ptr [rax]
0x18000c08c  mov     [rbx+8], ecx
0x18000c08f  lea     rcx, _TraceLoggingMetadata
0x18000c096  mov     dword ptr [rbx+0Ch], 2
0x18000c09d  mov     [rbx+10h], rdx
0x18000c0a1  movzx   eax, word ptr [rdx]
0x18000c0a4  mov     [rbx+18h], eax
0x18000c0a7  lea     rax, _TraceLoggingMetadataEnd
0x18000c0ae  sub     eax, ecx
0x18000c0b0  mov     dword ptr [rbx+1Ch], 1
0x18000c0b7  mov     [rsp+48h+arg_18], eax
0x18000c0bb  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x18000c0c2  mov     eax, [rsp+48h+arg_18]
0x18000c0c6  mov     eax, 0C000000Dh
0x18000c0cb  cmp     [rdi+28h], rcx
0x18000c0cf  jnz     short loc_18000C116
0x18000c0d1  mov     rdx, rbx
0x18000c0d4  call    ExtractAggregateFieldTypes
0x18000c0d9  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000c0de  test    al, al
0x18000c0e0  jz      short loc_18000C0F3
0x18000c0e2  mov     r9, rbx
0x18000c0e5  mov     byte ptr [rsp+48h+UserDataCount], al
0x18000c0e9  mov     rcx, rdi
0x18000c0ec  call    InsertEventEntryInLookUpTable
0x18000c0f1  jmp     short loc_18000C116
0x18000c0f3  mov     rcx, [rdi+20h]; RegHandle
0x18000c0f7  xor     r9d, r9d; RelatedActivityId
0x18000c0fa  mov     [rsp+48h+UserData], rbx; UserData
0x18000c0ff  xor     r8d, r8d; ActivityId
0x18000c102  mov     [rsp+48h+UserDataCount], 5; UserDataCount
0x18000c10a  call    cs:__imp_EtwWriteTransfer
0x18000c111  nop     dword ptr [rax+rax+00h]
0x18000c116  mov     rbx, [rsp+48h+arg_0]
0x18000c11b  add     rsp, 40h
0x18000c11f  pop     rdi
0x18000c120  retn
```
