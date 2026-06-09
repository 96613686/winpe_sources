# EACreateAggregateEvent

- ea: `0x1800044c0`
- end: `0x180004b28`
- name: `EACreateAggregateEvent`
- size: `1640`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003630`
- `0x1800044c0`
- `0x180005940`
- `0x1800072e0`
- `0x180007b5e`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004945`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800049a1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004945`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800049a1`
- `ntdll!RtlAllocateWnfSerializationGroup` at `0x18000480e`
- `ntdll!RtlAllocateWnfSerializationGroup` at `0x18000480e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800048f8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004969`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800048f8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004969`
- `ntdll!RtlFreeHeap` at `0x1800049be`
- `ntdll!RtlFreeHeap` at `0x1800049db`
- `ntdll!RtlFreeHeap` at `0x1800049f8`
- `ntdll!RtlFreeHeap` at `0x180004a13`
- `ntdll!RtlFreeHeap` at `0x180004a2b`
- `ntdll!RtlFreeHeap` at `0x1800049be`
- `ntdll!RtlFreeHeap` at `0x1800049db`
- `ntdll!RtlFreeHeap` at `0x1800049f8`
- `ntdll!RtlFreeHeap` at `0x180004a13`
- `ntdll!RtlFreeHeap` at `0x180004a2b`
- `ntdll!RtlAllocateHeap` at `0x1800046c9`
- `ntdll!RtlAllocateHeap` at `0x180004719`
- `ntdll!RtlAllocateHeap` at `0x180004766`
- `ntdll!RtlAllocateHeap` at `0x1800047b2`
- `ntdll!RtlAllocateHeap` at `0x1800046c9`
- `ntdll!RtlAllocateHeap` at `0x180004719`
- `ntdll!RtlAllocateHeap` at `0x180004766`
- `ntdll!RtlAllocateHeap` at `0x1800047b2`
- `ntdll!RtlInitializeSRWLock` at `0x180004808`
- `ntdll!RtlInitializeSRWLock` at `0x180004808`
- `ntdll!RtlNtStatusToDosError` at `0x180004b08`
- `ntdll!RtlNtStatusToDosError` at `0x180004b08`
- `ntdll!RtlInsertEntryHashTable` at `0x180004926`
- `ntdll!RtlInsertEntryHashTable` at `0x180004926`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000498d`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000498d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004585`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800046a1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004b00`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004585`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800046a1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004b00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000496f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000496f`

## pseudocode

```c
ULONG __fastcall EACreateAggregateEvent(__int64 a1, __int64 *a2)
{
  __int64 v4; // rdi
  NTSTATUS v5; // ebx
  int v6; // ecx
  unsigned int v7; // eax
  PVOID Heap; // rax
  _OWORD *v9; // rsi
  _OWORD *v10; // rax
  _DWORD *v11; // r15
  _BYTE *v12; // r14
  size_t v13; // r12
  _BYTE *v14; // rax
  unsigned int v15; // r8d
  __int64 v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  char inserted; // al
  unsigned int v21; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v22; // [rsp+34h] [rbp-75h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-71h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-61h] BYREF
  __int16 *v25; // [rsp+58h] [rbp-51h]
  int v26; // [rsp+60h] [rbp-49h]
  int v27; // [rsp+64h] [rbp-45h]
  unsigned int *v28; // [rsp+68h] [rbp-41h]
  __int64 v29; // [rsp+70h] [rbp-39h]
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+80h] [rbp-29h] BYREF
  void *v31; // [rsp+90h] [rbp-19h]
  int v32; // [rsp+98h] [rbp-11h]
  int v33; // [rsp+9Ch] [rbp-Dh]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+A0h] [rbp-9h]
  __int64 v35; // [rsp+A8h] [rbp-1h]
  unsigned int *v36; // [rsp+B0h] [rbp+7h]
  __int64 v37; // [rsp+B8h] [rbp+Fh]

  v4 = 0;
  if ( (unsigned int)dword_180012000 > 4 )
  {
    *(_DWORD *)&EventDescriptor.Level = 260;
    UserData.Ptr = (ULONGLONG)off_180012008;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v25 = &word_18000F42E;
    UserData.Reserved = 2;
    v26 = 26;
    v27 = 1;
    v21 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
  }
  if ( !a2 )
  {
    v5 = -1073741811;
    goto LABEL_69;
  }
  if ( a1 )
  {
    if ( (*(_DWORD *)(a1 + 8) & 0xFFFFFFF0) != 0 )
    {
      v6 = 200;
      goto LABEL_21;
    }
    v7 = *(_DWORD *)(a1 + 12);
    if ( v7 > 0x20 )
    {
      v6 = 300;
      goto LABEL_21;
    }
    if ( *(_DWORD *)a1 || *(_DWORD *)(a1 + 4) )
    {
      if ( !v7 )
        goto LABEL_18;
    }
    else if ( !v7 )
    {
      v6 = 300;
      goto LABEL_21;
    }
    if ( !*(_QWORD *)(a1 + 16) )
    {
      v6 = 400;
      goto LABEL_21;
    }
LABEL_18:
    if ( !*(_QWORD *)(a1 + 32) && !*(_QWORD *)(a1 + 40) )
    {
      v6 = 500;
      goto LABEL_21;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA0u);
    v4 = (__int64)Heap;
    if ( !Heap )
    {
      v5 = -1073741801;
      goto LABEL_69;
    }
    memset_0(Heap, 0, 0xA0u);
    v9 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x38u);
    if ( !v9 )
    {
      v5 = -1073741801;
LABEL_68:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)v4);
      v4 = 0;
      goto LABEL_69;
    }
    *v9 = 0;
    v9[1] = 0;
    v9[2] = 0;
    *((_QWORD *)v9 + 6) = 0;
    if ( *(_DWORD *)a1 || *(_DWORD *)(a1 + 4) )
    {
      v10 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x28u);
      *(_QWORD *)v9 = v10;
      if ( !v10 )
      {
        v5 = -1073741801;
LABEL_65:
        if ( *(_QWORD *)v9 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)v9);
          *(_QWORD *)v9 = 0;
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
        goto LABEL_68;
      }
      *v10 = 0;
      v10[1] = 0;
      *((_QWORD *)v10 + 4) = 0;
    }
    v11 = 0;
    v12 = 0;
    if ( *(_DWORD *)(a1 + 12) )
    {
      v11 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x38u);
      if ( !v11 )
      {
        v5 = -1073741801;
        goto LABEL_65;
      }
      v13 = 56LL * *(unsigned int *)(a1 + 12);
      v14 = (_BYTE *)EaLibAllocate(v13);
      v12 = v14;
      if ( !v14 )
      {
        v5 = -1073741801;
LABEL_64:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
        goto LABEL_65;
      }
      memset_0(v14, 0, v13);
    }
    *(_OWORD *)(v4 + 80) = 0;
    RtlInitializeSRWLock();
    *(_DWORD *)(v4 + 144) = RtlAllocateWnfSerializationGroup();
    *(_DWORD *)(v4 + 108) = 0;
    *(_QWORD *)(v4 + 56) = v9;
    *(_QWORD *)(v4 + 72) = *(_QWORD *)(a1 + 48);
    *(_QWORD *)(v4 + 24) = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(v4 + 32) = *(_QWORD *)(a1 + 40);
    *(_QWORD *)(v4 + 40) = 0;
    *(_QWORD *)(v4 + 48) = 0;
    if ( *(_QWORD *)v9 )
    {
      *(_QWORD *)(*(_QWORD *)v9 + 8LL) = *(_QWORD *)a1;
      *(_DWORD *)(*(_QWORD *)v9 + 20LL) = *(_DWORD *)(a1 + 8);
    }
    if ( *(_DWORD *)(a1 + 12) )
    {
      *v11 = 1;
      v15 = 0;
      v11[2] = *(_DWORD *)(a1 + 24);
      v11[3] = *(_DWORD *)(a1 + 12);
      for ( *((_QWORD *)v11 + 2) = v12; v15 < *(_DWORD *)(a1 + 12); v12[v17 + 48] = 1 )
      {
        v16 = v15++;
        v17 = 56 * v16;
        *(_DWORD *)&v12[v17] = 0;
        *(_QWORD *)&v12[v17 + 16] = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8 * v16);
      }
      *((_QWORD *)v9 + 1) = v11;
    }
    if ( !*(_DWORD *)a1 && !*(_DWORD *)(a1 + 4) )
      *(_BYTE *)(v4 + 64) = 1;
    v18 = *(_DWORD *)(v4 + 140);
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
    {
      v18 |= 1u;
      *(_DWORD *)(v4 + 140) = v18;
    }
    if ( (*(_BYTE *)(a1 + 8) & 2) != 0 )
      *(_DWORD *)(v4 + 140) = v18 | 2;
    *(_DWORD *)(v4 + 140) &= ~8u;
    *(_DWORD *)(v4 + 136) = 1;
    RtlAcquireSRWLockExclusive(AggregateEventListLock);
    dword_1800121B8 = GetCurrentThreadId();
    if ( qword_180012148 )
    {
      inserted = RtlInsertEntryHashTable(qword_180012148, v4, v4, 0);
      dword_1800121B8 = 0;
      if ( !inserted )
      {
        v5 = -1073741670;
        goto LABEL_61;
      }
      RtlReleaseSRWLockExclusive(AggregateEventListLock);
      v5 = EaiEnableAggregateEvent(v4);
      if ( v5 >= 0 )
      {
        *a2 = v4;
        goto LABEL_69;
      }
      RtlAcquireSRWLockExclusive(AggregateEventListLock);
      dword_1800121B8 = GetCurrentThreadId();
      if ( qword_180012148 )
        RtlRemoveEntryHashTable(qword_180012148, v4, 0);
    }
    else
    {
      v5 = -1073741595;
    }
    dword_1800121B8 = 0;
LABEL_61:
    RtlReleaseSRWLockExclusive(AggregateEventListLock);
    if ( v12 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
    if ( !v11 )
      goto LABEL_65;
    goto LABEL_64;
  }
  v6 = 100;
LABEL_21:
  if ( (unsigned int)dword_180012000 > 2 )
  {
    v21 = v6;
    v28 = &v21;
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_180012008;
    v29 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180012008;
    v25 = (__int16 *)&dword_18000EDF4;
    UserData.Reserved = 2;
    v26 = 40;
    v27 = 1;
    v22 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  v5 = -1073741811;
LABEL_69:
  if ( (unsigned int)dword_180012000 > 4 )
  {
    *(_QWORD *)&EventDescriptor.Id = v4;
    p_EventDescriptor = &EventDescriptor;
    v35 = 8;
    v36 = &v22;
    v30.Ptr = (ULONGLONG)off_180012008;
    v22 = v5;
    v37 = 4;
    UserData.Ptr = 0x2040B000000LL;
    *(_QWORD *)&UserData.Size = 0;
    v30.Size = *(unsigned __int16 *)off_180012008;
    v31 = &unk_18000F108;
    v30.Reserved = 2;
    v32 = 48;
    v33 = 1;
    v21 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 4u, &v30);
  }
  return RtlNtStatusToDosError(v5);
}

```

## disassembly

```asm
0x1800044c0  push    rbp
0x1800044c2  push    rbx
0x1800044c3  push    rsi
0x1800044c4  push    rdi
0x1800044c5  push    r12
0x1800044c7  lea     rbp, [rsp-37h]
0x1800044cc  sub     rsp, 0E0h
0x1800044d3  mov     rax, cs:__security_cookie
0x1800044da  xor     rax, rsp
0x1800044dd  mov     [rbp+57h+var_40], rax
0x1800044e1  mov     eax, cs:dword_180012000
0x1800044e7  lea     rsi, _TraceLoggingMetadataEnd
0x1800044ee  xor     r12d, r12d
0x1800044f1  mov     [rsp+100h+arg_10], r13
0x1800044f9  mov     r13, rdx
0x1800044fc  mov     rbx, rcx
0x1800044ff  lea     rdx, _TraceLoggingMetadata
0x180004506  mov     edi, r12d
0x180004509  cmp     eax, 4
0x18000450c  jbe     loc_180004592
0x180004512  movzx   eax, cs:word_18000F424
0x180004519  xor     r9d, r9d; RelatedActivityId
0x18000451c  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000451f  xor     r8d, r8d; ActivityId
0x180004522  mov     rax, cs:off_180012008
0x180004529  mov     [rbp+57h+var_B8.Ptr], rax
0x18000452d  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180004534  mov     [rbp+57h+EventDescriptor.Keyword], r12
0x180004538  movzx   eax, word ptr [rax]
0x18000453b  mov     [rbp+57h+var_B8.Size], eax
0x18000453e  lea     rax, word_18000F42E
0x180004545  mov     [rbp+57h+var_A8], rax
0x180004549  mov     rax, rsi
0x18000454c  sub     eax, edx
0x18000454e  mov     dword ptr [rbp+57h+var_B8.0Ch], 2
0x180004555  mov     [rbp+57h+var_A0], 1Ah
0x18000455c  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180004560  mov     [rbp+57h+var_9C], 1
0x180004567  mov     [rbp+57h+var_D0], eax
0x18000456a  mov     eax, [rbp+57h+var_D0]
0x18000456d  mov     rcx, cs:RegHandle; RegHandle
0x180004574  lea     rax, [rbp+57h+var_B8]
0x180004578  mov     [rsp+100h+UserData], rax; UserData
0x18000457d  mov     [rsp+100h+UserDataCount], 2; UserDataCount
0x180004585  call    cs:__imp_EventWriteTransfer
0x18000458b  lea     rdx, _TraceLoggingMetadata
0x180004592  test    r13, r13
0x180004595  jnz     short loc_1800045A1
0x180004597  mov     ebx, 0C000000Dh
0x18000459c  jmp     loc_180004A4B
0x1800045a1  test    rbx, rbx
0x1800045a4  jnz     short loc_1800045AD
0x1800045a6  mov     ecx, 64h ; 'd'
0x1800045ab  jmp     short loc_18000460C
0x1800045ad  test    dword ptr [rbx+8], 0FFFFFFF0h
0x1800045b4  jz      short loc_1800045BD
0x1800045b6  mov     ecx, 0C8h
0x1800045bb  jmp     short loc_18000460C
0x1800045bd  mov     eax, [rbx+0Ch]
0x1800045c0  cmp     eax, 20h ; ' '
0x1800045c3  jbe     short loc_1800045CC
0x1800045c5  mov     ecx, 12Ch
0x1800045ca  jmp     short loc_18000460C
0x1800045cc  cmp     [rbx], r12d
0x1800045cf  jnz     short loc_1800045E2
0x1800045d1  cmp     [rbx+4], r12d
0x1800045d5  jnz     short loc_1800045E2
0x1800045d7  test    eax, eax
0x1800045d9  jnz     short loc_1800045E6
0x1800045db  mov     ecx, 12Ch
0x1800045e0  jmp     short loc_18000460C
0x1800045e2  test    eax, eax
0x1800045e4  jz      short loc_1800045F3
0x1800045e6  cmp     [rbx+10h], r12
0x1800045ea  jnz     short loc_1800045F3
0x1800045ec  mov     ecx, 190h
0x1800045f1  jmp     short loc_18000460C
0x1800045f3  cmp     [rbx+20h], r12
0x1800045f7  jnz     loc_1800046B1
0x1800045fd  cmp     [rbx+28h], r12
0x180004601  jnz     loc_1800046B1
0x180004607  mov     ecx, 1F4h
0x18000460c  mov     eax, cs:dword_180012000
0x180004612  cmp     eax, 2
0x180004615  jbe     loc_1800046A7
0x18000461b  mov     [rbp+57h+var_D0], ecx
0x18000461e  lea     rax, [rbp+57h+var_D0]
0x180004622  mov     [rbp+57h+var_98], rax
0x180004626  xor     r9d, r9d; RelatedActivityId
0x180004629  movzx   eax, cs:word_18000EDEA
0x180004630  xor     r8d, r8d; ActivityId
0x180004633  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180004636  mov     rax, cs:off_180012008
0x18000463d  mov     [rbp+57h+var_B8.Ptr], rax
0x180004641  mov     [rbp+57h+var_90], 4
0x180004649  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180004650  mov     [rbp+57h+EventDescriptor.Keyword], r12
0x180004654  movzx   eax, word ptr [rax]
0x180004657  mov     [rbp+57h+var_B8.Size], eax
0x18000465a  lea     rax, dword_18000EDF4
0x180004661  mov     [rbp+57h+var_A8], rax
0x180004665  mov     rax, rsi
0x180004668  sub     eax, edx
0x18000466a  mov     dword ptr [rbp+57h+var_B8.0Ch], 2
0x180004671  mov     [rbp+57h+var_A0], 28h ; '('
0x180004678  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000467c  mov     [rbp+57h+var_9C], 1
0x180004683  mov     [rbp+57h+var_CC], eax
0x180004686  mov     eax, [rbp+57h+var_CC]
0x180004689  mov     rcx, cs:RegHandle; RegHandle
0x180004690  lea     rax, [rbp+57h+var_B8]
0x180004694  mov     [rsp+100h+UserData], rax; UserData
0x180004699  mov     [rsp+100h+UserDataCount], 3; UserDataCount
0x1800046a1  call    cs:__imp_EventWriteTransfer
0x1800046a7  mov     ebx, 0C000000Dh
0x1800046ac  jmp     loc_180004A4B
0x1800046b1  mov     rcx, gs:60h
0x1800046ba  mov     edx, 8; Flags
0x1800046bf  mov     r8d, 0A0h; Size
0x1800046c5  mov     rcx, [rcx+30h]; HeapHandle
0x1800046c9  call    cs:__imp_RtlAllocateHeap
0x1800046cf  mov     rdi, rax
0x1800046d2  test    rax, rax
0x1800046d5  jnz     short loc_1800046E1
0x1800046d7  mov     ebx, 0C0000017h
0x1800046dc  jmp     loc_180004A4B
0x1800046e1  mov     [rsp+100h+var_28], r14
0x1800046e9  xor     edx, edx; Val
0x1800046eb  mov     r8d, 0A0h; Size
0x1800046f1  mov     [rsp+100h+var_30], r15
0x1800046f9  mov     rcx, rdi; void *
0x1800046fc  call    memset_0
0x180004701  mov     rcx, gs:60h
0x18000470a  mov     edx, 8; Flags
0x18000470f  mov     r8d, 38h ; '8'; Size
0x180004715  mov     rcx, [rcx+30h]; HeapHandle
0x180004719  call    cs:__imp_RtlAllocateHeap
0x18000471f  mov     rsi, rax
0x180004722  test    rax, rax
0x180004725  jnz     short loc_180004731
0x180004727  mov     ebx, 0C0000017h
0x18000472c  jmp     loc_180004A19
0x180004731  xorps   xmm0, xmm0
0x180004734  xor     eax, eax
0x180004736  movups  xmmword ptr [rsi], xmm0
0x180004739  movups  xmmword ptr [rsi+10h], xmm0
0x18000473d  movups  xmmword ptr [rsi+20h], xmm0
0x180004741  mov     [rsi+30h], rax
0x180004745  cmp     [rbx], eax
0x180004747  jnz     short loc_18000474E
0x180004749  cmp     [rbx+4], eax
0x18000474c  jz      short loc_18000478E
0x18000474e  mov     rcx, gs:60h
0x180004757  mov     edx, 8; Flags
0x18000475c  mov     r8d, 28h ; '('; Size
0x180004762  mov     rcx, [rcx+30h]; HeapHandle
0x180004766  call    cs:__imp_RtlAllocateHeap
0x18000476c  mov     [rsi], rax
0x18000476f  test    rax, rax
0x180004772  jnz     short loc_18000477E
0x180004774  mov     ebx, 0C0000017h
0x180004779  jmp     loc_1800049E1
0x18000477e  xorps   xmm0, xmm0
0x180004781  xor     ecx, ecx
0x180004783  movups  xmmword ptr [rax], xmm0
0x180004786  movups  xmmword ptr [rax+10h], xmm0
0x18000478a  mov     [rax+20h], rcx
0x18000478e  mov     r15, r12
0x180004791  mov     r14, r12
0x180004794  cmp     [rbx+0Ch], r12d
0x180004798  jbe     short loc_1800047FE
0x18000479a  mov     rcx, gs:60h
0x1800047a3  mov     edx, 8; Flags
0x1800047a8  mov     r8d, 38h ; '8'; Size
0x1800047ae  mov     rcx, [rcx+30h]; HeapHandle
0x1800047b2  call    cs:__imp_RtlAllocateHeap
0x1800047b8  mov     r15, rax
0x1800047bb  test    rax, rax
0x1800047be  jnz     short loc_1800047CA
0x1800047c0  mov     ebx, 0C0000017h
0x1800047c5  jmp     loc_1800049E1
0x1800047ca  mov     eax, [rbx+0Ch]
0x1800047cd  imul    r12, rax, 38h ; '8'
0x1800047d1  mov     rcx, r12
0x1800047d4  call    EaLibAllocate
0x1800047d9  mov     r14, rax
0x1800047dc  test    rax, rax
0x1800047df  jnz     short loc_1800047EE
0x1800047e1  mov     ebx, 0C0000017h
0x1800047e6  xor     r12d, r12d
0x1800047e9  jmp     loc_1800049C9
0x1800047ee  mov     r8, r12; Size
0x1800047f1  xor     edx, edx; Val
0x1800047f3  mov     rcx, rax; void *
0x1800047f6  call    memset_0
0x1800047fb  xor     r12d, r12d
0x1800047fe  lea     rcx, [rdi+50h]
0x180004802  xorps   xmm0, xmm0
0x180004805  movups  xmmword ptr [rcx], xmm0
0x180004808  call    cs:__imp_RtlInitializeSRWLock
0x18000480e  call    cs:__imp_RtlAllocateWnfSerializationGroup
0x180004814  mov     [rdi+90h], eax
0x18000481a  mov     [rdi+6Ch], r12d
0x18000481e  mov     [rdi+38h], rsi
0x180004822  mov     rax, [rbx+30h]
0x180004826  mov     [rdi+48h], rax
0x18000482a  mov     rax, [rbx+20h]
0x18000482e  mov     [rdi+18h], rax
0x180004832  mov     rax, [rbx+28h]
0x180004836  mov     [rdi+20h], rax
0x18000483a  mov     [rdi+28h], r12
0x18000483e  mov     [rdi+30h], r12
0x180004842  mov     rcx, [rsi]
0x180004845  test    rcx, rcx
0x180004848  jz      short loc_18000485A
0x18000484a  mov     rax, [rbx]
0x18000484d  mov     [rcx+8], rax
0x180004851  mov     rcx, [rsi]
0x180004854  mov     eax, [rbx+8]
0x180004857  mov     [rcx+14h], eax
0x18000485a  cmp     dword ptr [rbx+0Ch], 0
0x18000485e  jbe     short loc_1800048AD
0x180004860  mov     dword ptr [r15], 1
0x180004867  mov     r8d, r12d
0x18000486a  mov     eax, [rbx+18h]
0x18000486d  mov     [r15+8], eax
0x180004871  mov     eax, [rbx+0Ch]
0x180004874  mov     [r15+0Ch], eax
0x180004878  mov     [r15+10h], r14
0x18000487c  cmp     dword ptr [rbx+0Ch], 0
0x180004880  jbe     short loc_1800048A9
0x180004882  mov     ecx, r8d
0x180004885  inc     r8d
0x180004888  imul    rdx, rcx, 38h ; '8'
0x18000488c  mov     [rdx+r14], r12d
0x180004890  mov     rax, [rbx+10h]
0x180004894  mov     rcx, [rax+rcx*8]
0x180004898  mov     [rdx+r14+10h], rcx
0x18000489d  mov     byte ptr [rdx+r14+30h], 1
0x1800048a3  cmp     r8d, [rbx+0Ch]
0x1800048a7  jb      short loc_180004882
0x1800048a9  mov     [rsi+8], r15
0x1800048ad  cmp     dword ptr [rbx], 0
0x1800048b0  jnz     short loc_1800048BC
0x1800048b2  cmp     dword ptr [rbx+4], 0
0x1800048b6  jnz     short loc_1800048BC
0x1800048b8  mov     byte ptr [rdi+40h], 1
0x1800048bc  test    byte ptr [rbx+8], 1
0x1800048c0  mov     eax, [rdi+8Ch]
0x1800048c6  jz      short loc_1800048D1
0x1800048c8  or      eax, 1
0x1800048cb  mov     [rdi+8Ch], eax
0x1800048d1  test    byte ptr [rbx+8], 2
0x1800048d5  jz      short loc_1800048E0
0x1800048d7  or      eax, 2
0x1800048da  mov     [rdi+8Ch], eax
0x1800048e0  and     dword ptr [rdi+8Ch], 0FFFFFFF7h
0x1800048e7  lea     rcx, AggregateEventListLock
0x1800048ee  mov     dword ptr [rdi+88h], 1
0x1800048f8  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800048fe  call    cs:__imp_GetCurrentThreadId
0x180004904  mov     rcx, cs:qword_180012148
0x18000490b  mov     cs:dword_1800121B8, eax
0x180004911  test    rcx, rcx
0x180004914  jnz     short loc_18000491D
0x180004916  mov     ebx, 0C00000E5h
0x18000491b  jmp     short loc_180004993
0x18000491d  xor     r9d, r9d
0x180004920  mov     r8, rdi
0x180004923  mov     rdx, rdi
0x180004926  call    cs:__imp_RtlInsertEntryHashTable
0x18000492c  mov     cs:dword_1800121B8, r12d
0x180004933  lea     rcx, AggregateEventListLock
0x18000493a  test    al, al
0x18000493c  jnz     short loc_180004945
0x18000493e  mov     ebx, 0C000009Ah
0x180004943  jmp     short loc_1800049A1
0x180004945  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000494b  mov     rcx, rdi
0x18000494e  call    EaiEnableAggregateEvent
0x180004953  mov     ebx, eax
0x180004955  test    eax, eax
0x180004957  js      short loc_180004962
0x180004959  mov     [r13+0], rdi
0x18000495d  jmp     loc_180004A34
0x180004962  lea     rcx, AggregateEventListLock
0x180004969  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000496f  call    cs:__imp_GetCurrentThreadId
0x180004975  mov     rcx, cs:qword_180012148
0x18000497c  mov     cs:dword_1800121B8, eax
0x180004982  test    rcx, rcx
0x180004985  jz      short loc_180004993
0x180004987  xor     r8d, r8d
0x18000498a  mov     rdx, rdi
0x18000498d  call    cs:__imp_RtlRemoveEntryHashTable
0x180004993  mov     cs:dword_1800121B8, r12d
0x18000499a  lea     rcx, AggregateEventListLock
0x1800049a1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800049a7  test    r14, r14
0x1800049aa  jz      short loc_1800049C4
  ... truncated ...
```
