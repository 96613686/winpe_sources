# EaiExtractEventAggregation

- ea: `0x1800011e0`
- end: `0x180001398`
- name: `EaiExtractEventAggregation`
- size: `440`
- prototype: `__int64 __fastcall(__int64, char, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001160`
- `0x180001170`

## callees

- `0x1800011e0`
- `0x180001730`
- `0x1800072e0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockShared` at `0x18000122c`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000122c`
- `ntdll!RtlReleaseSRWLockShared` at `0x180001260`
- `ntdll!RtlReleaseSRWLockShared` at `0x180001291`
- `ntdll!RtlReleaseSRWLockShared` at `0x180001260`
- `ntdll!RtlReleaseSRWLockShared` at `0x180001291`
- `ntdll!RtlLookupEntryHashTable` at `0x180001244`
- `ntdll!RtlLookupEntryHashTable` at `0x180001244`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000136d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000136d`

## pseudocode

```c
__int64 __fastcall EaiExtractEventAggregation(__int64 a1, char a2, _QWORD *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rbx
  _DWORD v10[2]; // [rsp+30h] [rbp-88h] BYREF
  __int64 v11; // [rsp+38h] [rbp-80h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-68h] BYREF
  __int16 *v14; // [rsp+60h] [rbp-58h]
  int v15; // [rsp+68h] [rbp-50h]
  int v16; // [rsp+6Ch] [rbp-4Ch]
  __int64 *v17; // [rsp+70h] [rbp-48h]
  __int64 v18; // [rsp+78h] [rbp-40h]
  _DWORD *v19; // [rsp+80h] [rbp-38h]
  __int64 v20; // [rsp+88h] [rbp-30h]

  if ( !a1 )
  {
    v6 = -1073741811;
LABEL_11:
    if ( (unsigned int)dword_180012000 > 2 )
    {
      v11 = a1;
      v17 = &v11;
      v18 = 8;
      v19 = v10;
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_180012008;
      v10[0] = v6;
      v20 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_180012008;
      v14 = word_18000F09A;
      UserData.Reserved = 2;
      v15 = 50;
      v16 = 1;
      v10[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
    }
    return v6;
  }
  if ( !a3 )
  {
    v6 = -1073741811;
    goto LABEL_11;
  }
  RtlAcquireSRWLockShared(AggregateEventListLock);
  if ( !qword_180012148 || (v7 = RtlLookupEntryHashTable(qword_180012148, a1, 0), (v8 = v7) == 0) )
  {
    RtlReleaseSRWLockShared(AggregateEventListLock);
    v6 = -1073741275;
    goto LABEL_11;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v7 + 136));
  RtlReleaseSRWLockShared(AggregateEventListLock);
  *a3 = *(_QWORD *)(v8 + 56);
  if ( a2 )
    *(_DWORD *)(v8 + 140) |= 8u;
  EaiReleaseAggregateEvent(v8);
  return 0;
}

```

## disassembly

```asm
0x1800011e0  mov     [rsp+arg_8], rbx
0x1800011e5  push    rbp
0x1800011e6  push    rsi
0x1800011e7  push    rdi
0x1800011e8  sub     rsp, 0A0h
0x1800011ef  mov     rax, cs:__security_cookie
0x1800011f6  xor     rax, rsp
0x1800011f9  mov     [rsp+0B8h+var_28], rax
0x180001201  mov     rsi, r8
0x180001204  movzx   ebp, dl
0x180001207  mov     rdi, rcx
0x18000120a  test    rcx, rcx
0x18000120d  jnz     short loc_180001219
0x18000120f  mov     ebx, 0C000000Dh
0x180001214  jmp     loc_18000129C
0x180001219  test    rsi, rsi
0x18000121c  jnz     short loc_180001225
0x18000121e  mov     ebx, 0C000000Dh
0x180001223  jmp     short loc_18000129C
0x180001225  lea     rcx, AggregateEventListLock
0x18000122c  call    cs:__imp_RtlAcquireSRWLockShared
0x180001232  mov     rcx, cs:qword_180012148
0x180001239  test    rcx, rcx
0x18000123c  jz      short loc_18000128A
0x18000123e  xor     r8d, r8d
0x180001241  mov     rdx, rdi
0x180001244  call    cs:__imp_RtlLookupEntryHashTable
0x18000124a  mov     rbx, rax
0x18000124d  test    rax, rax
0x180001250  jz      short loc_18000128A
0x180001252  lock inc dword ptr [rax+88h]
0x180001259  lea     rcx, AggregateEventListLock
0x180001260  call    cs:__imp_RtlReleaseSRWLockShared
0x180001266  mov     rax, [rbx+38h]
0x18000126a  xor     edi, edi
0x18000126c  mov     [rsi], rax
0x18000126f  test    bpl, bpl
0x180001272  jz      short loc_18000127B
0x180001274  or      dword ptr [rbx+8Ch], 8
0x18000127b  mov     rcx, rbx
0x18000127e  call    EaiReleaseAggregateEvent
0x180001283  mov     eax, edi
0x180001285  jmp     loc_180001375
0x18000128a  lea     rcx, AggregateEventListLock
0x180001291  call    cs:__imp_RtlReleaseSRWLockShared
0x180001297  mov     ebx, 0C0000225h
0x18000129c  mov     eax, cs:dword_180012000
0x1800012a2  cmp     eax, 2
0x1800012a5  jbe     loc_180001373
0x1800012ab  mov     [rsp+0B8h+var_80], rdi
0x1800012b0  lea     rax, [rsp+0B8h+var_80]
0x1800012b5  mov     [rsp+0B8h+var_48], rax
0x1800012ba  lea     rcx, _TraceLoggingMetadataEnd
0x1800012c1  lea     rax, [rsp+0B8h+var_88]
0x1800012c6  mov     [rsp+0B8h+var_40], 8
0x1800012cf  mov     [rsp+0B8h+var_38], rax
0x1800012d7  lea     rdx, [rsp+0B8h+EventDescriptor]; EventDescriptor
0x1800012dc  movzx   eax, cs:word_18000F090
0x1800012e3  xor     edi, edi
0x1800012e5  mov     dword ptr [rsp+0B8h+EventDescriptor.Level], eax
0x1800012e9  xor     r9d, r9d; RelatedActivityId
0x1800012ec  mov     rax, cs:off_180012008
0x1800012f3  xor     r8d, r8d; ActivityId
0x1800012f6  mov     [rsp+0B8h+var_68.Ptr], rax
0x1800012fb  mov     [rsp+0B8h+var_88], ebx
0x1800012ff  mov     [rsp+0B8h+var_30], 4
0x18000130b  mov     dword ptr [rsp+0B8h+EventDescriptor.Id], 0B000000h
0x180001313  mov     [rsp+0B8h+EventDescriptor.Keyword], rdi
0x180001318  movzx   eax, word ptr [rax]
0x18000131b  mov     [rsp+0B8h+var_68.Size], eax
0x18000131f  lea     rax, word_18000F09A
0x180001326  mov     [rsp+0B8h+var_58], rax
0x18000132b  lea     rax, _TraceLoggingMetadata
0x180001332  sub     ecx, eax
0x180001334  mov     dword ptr [rsp+0B8h+var_68.0Ch], 2
0x18000133c  mov     [rsp+0B8h+var_50], 32h ; '2'
0x180001344  lea     rax, [rsp+0B8h+var_68]
0x180001349  mov     [rsp+0B8h+var_4C], 1
0x180001351  mov     [rsp+0B8h+var_84], ecx
0x180001355  mov     ecx, [rsp+0B8h+var_84]
0x180001359  mov     rcx, cs:RegHandle; RegHandle
0x180001360  mov     [rsp+0B8h+UserData], rax; UserData
0x180001365  mov     [rsp+0B8h+UserDataCount], 4; UserDataCount
0x18000136d  call    cs:__imp_EventWriteTransfer
0x180001373  mov     eax, ebx
0x180001375  mov     rcx, [rsp+0B8h+var_28]
0x18000137d  xor     rcx, rsp; StackCookie
0x180001380  call    __security_check_cookie
0x180001385  mov     rbx, [rsp+0B8h+arg_8]
0x18000138d  add     rsp, 0A0h
0x180001394  pop     rdi
0x180001395  pop     rsi
0x180001396  pop     rbp
0x180001397  retn
```
