# BipWorkItemRundown(_BI_WORK_ITEM *)

- ea: `0x180058b20`
- end: `0x1800593a0`
- name: `?BipWorkItemRundown@@YAXPEAU_BI_WORK_ITEM@@@Z`
- size: `2176`
- prototype: `void __fastcall(struct _BI_WORK_ITEM *)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001027c`
- `0x180059ad0`

## callees

- `0x18000568c`
- `0x1800072f8`
- `0x18000d7c0`
- `0x18000da50`
- `0x180024ecc`
- `0x180032fc8`
- `0x18003d104`
- `0x18003dc6c`
- `0x180056154`
- `0x180058b20`
- `0x18006a8d4`
- `0x18006d364`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180058f30`
- `ntdll!RtlRemoveEntryHashTable` at `0x180058f30`
- `ntdll!RtlWaitForWnfMetaNotification` at `0x18005918f`
- `ntdll!RtlWaitForWnfMetaNotification` at `0x1800592d0`
- `ntdll!RtlWaitForWnfMetaNotification` at `0x180059326`
- `ntdll!RtlWaitForWnfMetaNotification` at `0x18005918f`
- `ntdll!RtlWaitForWnfMetaNotification` at `0x1800592d0`
- `ntdll!RtlWaitForWnfMetaNotification` at `0x180059326`
- `ntdll!NtDeleteWnfStateName` at `0x18005919c`
- `ntdll!NtDeleteWnfStateName` at `0x180059213`
- `ntdll!NtDeleteWnfStateName` at `0x1800592dd`
- `ntdll!NtDeleteWnfStateName` at `0x180059333`
- `ntdll!NtDeleteWnfStateName` at `0x18005919c`
- `ntdll!NtDeleteWnfStateName` at `0x180059213`
- `ntdll!NtDeleteWnfStateName` at `0x1800592dd`
- `ntdll!NtDeleteWnfStateName` at `0x180059333`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180058fd5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180058fd5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005903a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180059103`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005929d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180059363`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005903a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180059103`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005929d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180059363`
- `ntdll!TpWaitForTimer` at `0x180059122`
- `ntdll!TpWaitForTimer` at `0x180059122`
- `ntdll!RtlFreeHeap` at `0x180058f6b`
- `ntdll!RtlFreeHeap` at `0x180058f85`
- `ntdll!RtlFreeHeap` at `0x180058f6b`
- `ntdll!RtlFreeHeap` at `0x180058f85`
- `ntdll!TpPostWork` at `0x180059067`
- `ntdll!TpPostWork` at `0x180059067`
- `ntdll!RtlAllocateHeap` at `0x18005922a`
- `ntdll!RtlAllocateHeap` at `0x18005922a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180058c27`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180058f1d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180058c27`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180058f1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058fdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058fdb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180058fc0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180058fc0`

## pseudocode

```c
void __fastcall BipWorkItemRundown(struct _BI_WORK_ITEM *a1)
{
  __int64 v2; // rcx
  char *v3; // rcx
  __int64 v4; // rax
  char **v5; // rdx
  char *v6; // rcx
  __int64 v7; // rax
  char **v8; // rdx
  char *v9; // rcx
  __int64 v10; // rax
  char **v11; // rdx
  int v12; // ecx
  __int64 v13; // r14
  _DWORD *v14; // rcx
  _OWORD *v15; // rax
  __int64 v16; // r8
  _QWORD *v17; // rdx
  _OWORD *v18; // rax
  __int64 v19; // rdx
  _QWORD *v20; // rcx
  __int64 *v21; // rcx
  __int64 v22; // rax
  unsigned int v24; // eax
  _QWORD *v25; // rbx
  _QWORD *v26; // rdi
  void *v27; // r15
  void *v28; // r8
  struct _BI_LOCK *v29; // rdi
  unsigned int v30; // ebx
  __int64 v31; // r12
  _DWORD *v32; // r15
  DWORD CurrentThreadId; // eax
  _DWORD *v34; // r12
  char v35; // al
  int v36; // ebx
  unsigned int i; // ebx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v38; // rcx
  _QWORD *ThreadLocalStoragePointer; // rax
  int v40; // edi
  __int64 v41; // rbx
  _DWORD *v42; // r15
  __int64 v43; // rcx
  _DWORD *v44; // r12
  __int64 v45; // rdx
  int v46; // ecx
  __int64 v47; // rcx
  __int64 v48; // rcx
  _OWORD *Heap; // rdi
  _QWORD *v50; // rax
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v51; // rcx
  __int64 v52; // rax
  int v53; // ebx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rax
  int v57; // r13d
  unsigned int v58; // [rsp+30h] [rbp-39h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-19h] BYREF
  char *v61; // [rsp+60h] [rbp-9h]
  int v62; // [rsp+68h] [rbp-1h]
  int v63; // [rsp+6Ch] [rbp+3h]
  const unsigned __int16 *v64; // [rsp+70h] [rbp+7h]
  __int64 v65; // [rsp+78h] [rbp+Fh]
  char *v66; // [rsp+80h] [rbp+17h]
  __int64 v67; // [rsp+88h] [rbp+1Fh]

  if ( (unsigned int)dword_1800C3098 > 5 && (qword_1800C30A8 & 2) != 0 && (qword_1800C30B0 & 2) == qword_1800C30B0 )
  {
    v67 = 16;
    v66 = (char *)a1 + 32;
    v65 = 1;
    v64 = &qword_1800A1850;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 2;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v61 = byte_1800B34B1;
    UserData.Reserved = 2;
    v62 = 37;
    v63 = 1;
    v58 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  BipSystemStateCheckSetWorkItemNetworkRequest(a1, 0);
  BipAcquireGlobalLock(v2);
  v3 = (char *)a1 + 240;
  if ( *((_QWORD *)a1 + 30) && *((_QWORD *)a1 + 31) )
  {
    v4 = *(_QWORD *)v3;
    if ( *(char **)(*(_QWORD *)v3 + 8LL) != v3 )
      goto LABEL_82;
    v5 = (char **)*((_QWORD *)a1 + 31);
    if ( *v5 != v3 )
      goto LABEL_82;
    *v5 = (char *)v4;
    *(_QWORD *)(v4 + 8) = v5;
    *(_OWORD *)v3 = 0;
  }
  v6 = (char *)a1 + 256;
  if ( *((_QWORD *)a1 + 32) && *((_QWORD *)a1 + 33) )
  {
    v7 = *(_QWORD *)v6;
    if ( *(char **)(*(_QWORD *)v6 + 8LL) != v6 )
      goto LABEL_82;
    v8 = (char **)*((_QWORD *)a1 + 33);
    if ( *v8 != v6 )
      goto LABEL_82;
    *v8 = (char *)v7;
    *(_QWORD *)(v7 + 8) = v8;
    *(_OWORD *)v6 = 0;
  }
  v9 = (char *)a1 + 288;
  if ( *((_QWORD *)a1 + 36) && *((_QWORD *)a1 + 37) )
  {
    v10 = *(_QWORD *)v9;
    if ( *(char **)(*(_QWORD *)v9 + 8LL) != v9 )
      goto LABEL_82;
    v11 = (char **)*((_QWORD *)a1 + 37);
    if ( *v11 != v9 )
      goto LABEL_82;
    *v11 = (char *)v10;
    *(_QWORD *)(v10 + 8) = v11;
    *(_OWORD *)v9 = 0;
  }
  v12 = *((_DWORD *)a1 + 100);
  if ( !v12 || v12 == 2 )
  {
    v13 = *((_QWORD *)a1 + 10);
    if ( v13 )
    {
      v14 = (_DWORD *)*((_QWORD *)a1 + 11);
      if ( v14 )
      {
        *((_QWORD *)a1 + 11) = 0;
        v15 = (_OWORD *)((char *)a1 + 176);
        --v14[14];
        v16 = *((_QWORD *)a1 + 22);
        if ( *(struct _BI_WORK_ITEM **)(v16 + 8) != (struct _BI_WORK_ITEM *)((char *)a1 + 176) )
          goto LABEL_82;
        v17 = (_QWORD *)*((_QWORD *)a1 + 23);
        if ( (_OWORD *)*v17 != v15 )
          goto LABEL_82;
        *v17 = v16;
        *(_QWORD *)(v16 + 8) = v17;
        *v15 = 0;
        BipConditionallyDeletePackageApplication(v14);
      }
      v18 = (_OWORD *)((char *)a1 + 160);
      v19 = *((_QWORD *)a1 + 20);
      if ( *(struct _BI_WORK_ITEM **)(v19 + 8) != (struct _BI_WORK_ITEM *)((char *)a1 + 160) )
        goto LABEL_82;
      v20 = (_QWORD *)*((_QWORD *)a1 + 21);
      if ( (_OWORD *)*v20 != v18 )
        goto LABEL_82;
      *v20 = v19;
      *(_QWORD *)(v19 + 8) = v20;
      *v18 = 0;
      *((_QWORD *)a1 + 10) = 0;
      if ( *(_QWORD *)(v13 + 32) == v13 + 32
        && *(_QWORD *)(v13 + 64) == v13 + 64
        && !*(_DWORD *)(v13 + 572)
        && *(_DWORD *)(v13 + 576) == -1
        && *(_QWORD *)(v13 + 96) == v13 + 96
        && *(_QWORD *)(v13 + 48) == v13 + 48
        && (*(_BYTE *)(v13 + 604) & 2) == 0 )
      {
        if ( (unsigned int)dword_1800C3098 > 5 && (qword_1800C30A8 & 2) != 0 && (qword_1800C30B0 & 2) == qword_1800C30B0 )
        {
          v21 = (__int64 *)(v13 + 160);
          if ( v13 == -160 )
          {
            v21 = &qword_1800A1670;
            v24 = 2;
          }
          else
          {
            v22 = -1;
            while ( *((_WORD *)v21 + ++v22) != 0 )
              ;
            v24 = 2 * v22 + 2;
          }
          v65 = v24;
          *(_DWORD *)&EventDescriptor.Level = 5;
          UserData.Ptr = (ULONGLONG)off_1800C30A0;
          v64 = (const unsigned __int16 *)v21;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 2;
          UserData.Size = *(unsigned __int16 *)off_1800C30A0;
          v61 = byte_1800AF5DB;
          UserData.Reserved = 2;
          v62 = 36;
          v63 = 1;
          v58 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
        }
        RtlRemoveEntryHashTable(qword_1800C4380, v13, 0);
        v25 = *(_QWORD **)(v13 + 128);
        while ( v25 != (_QWORD *)(v13 + 128) )
        {
          v26 = v25;
          v27 = v25;
          v25 = (_QWORD *)*v25;
          v28 = (void *)v26[6];
          if ( v28 )
          {
            RtlFreeHeap(BipHeap, 0, v28);
            v26[6] = 0;
          }
          RtlFreeHeap(BipHeap, 0, v27);
        }
        v29 = qword_1800C45C0;
        v30 = 1 << *((_DWORD *)qword_1800C45C0 + 2);
        v31 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
        v32 = (_DWORD *)(v31 + 4);
        if ( *(_DWORD *)(v31 + 4) >= v30 && IsDebuggerPresent() )
          BipSyncDebugPrintLockBug(v29);
        RtlAcquireSRWLockExclusive(v29);
        CurrentThreadId = GetCurrentThreadId();
        *v32 |= v30;
        *((_DWORD *)v29 + 3) = CurrentThreadId;
        v34 = (_DWORD *)(v31 + 8);
        v35 = *((_BYTE *)v29 + 176);
        *v34 |= v30;
        if ( (v35 & 4) == 0
          && *((_WORD *)v29 + 16)
          && *((_WORD *)v29 + 17)
          && *((_WORD *)v29 + 18) < 0x64u
          && (v35 & 0x40) == 0 )
        {
          BipEnergyBudgetPackageDereferenced(v29, v13);
        }
        v36 = ~(1 << *((_DWORD *)v29 + 2));
        *v34 &= v36;
        *((_DWORD *)v29 + 3) = 0;
        RtlReleaseSRWLockExclusive(v29);
        *v32 &= v36;
        if ( (*(_BYTE *)(v13 + 604) & 0x10) != 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        ++dword_1800C4654;
        *(_BYTE *)(v13 + 604) |= 0x10u;
        TpPostWork(*(_QWORD *)(v13 + 592));
      }
    }
  }
  for ( i = 0; i < *((_DWORD *)a1 + 156); ++i )
    BipRemoveWorkItemEvent(a1, *((struct _BI_EVENT **)a1 + 4 * i + 79), (struct _LIST_ENTRY *)a1 + 2 * i + 40);
  BipRemoveWorkItemEvent(a1, *((struct _BI_EVENT **)a1 + 9), (struct _LIST_ENTRY *)a1 + 6);
  BipLockWatchdogContextDisarmWatchdog(v38);
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v40 = ~(1 << dword_1800C3CB0);
  dword_1800C3CB4 = 0;
  v41 = ThreadLocalStoragePointer[(unsigned int)tls_index];
  v42 = (_DWORD *)(v41 + 8);
  *(_DWORD *)(v41 + 8) &= v40;
  RtlReleaseSRWLockExclusive(&BipGlobalLock);
  v43 = *((_QWORD *)a1 + 66);
  v44 = (_DWORD *)(v41 + 4);
  *(_DWORD *)(v41 + 4) &= v40;
  if ( v43 )
    TpWaitForTimer(v43, 1);
  v45 = *((_QWORD *)a1 + 65);
  if ( v45 )
    BipWorkItemEaContextCheckQueueCleanup(a1, v45, 3);
  BipWorkItemEaContextCleanupQueuedContexts(a1);
  v46 = *((_DWORD *)a1 + 100);
  if ( (!v46 || v46 == 2) && (*((_DWORD *)a1 + 6) & 0x20000000) != 0 )
  {
    v47 = *((_QWORD *)a1 + 72);
    v58 = 0;
    RtlWaitForWnfMetaNotification(v47, 8, 5000, 1000, &v58);
    NtDeleteWnfStateName((char *)a1 + 576);
    *((_DWORD *)a1 + 6) &= ~0x20000000u;
  }
  v48 = *((unsigned int *)a1 + 100);
  if ( !(_DWORD)v48 || (v48 = (unsigned int)(v48 - 1), (_DWORD)v48 == 1) )
  {
    if ( *((_DWORD *)a1 + 148) || *((_DWORD *)a1 + 149) )
    {
      BipAcquireGlobalLock(v48);
      if ( (unsigned int)dword_1800C43B0 < 0x20 )
      {
        Heap = RtlAllocateHeap(BipHeap, 0, 0x28u);
        if ( !Heap )
        {
LABEL_84:
          BipLockWatchdogContextDisarmWatchdog(v51);
          v53 = ~(1 << dword_1800C3CB0);
          dword_1800C3CB4 = 0;
          *v42 &= v53;
          RtlReleaseSRWLockExclusive(&BipGlobalLock);
          *v44 &= v53;
          if ( !Heap )
          {
            v54 = *((_QWORD *)a1 + 74);
            v58 = 0;
            RtlWaitForWnfMetaNotification(v54, 8, 5000, 1000, &v58);
            NtDeleteWnfStateName((char *)a1 + 592);
          }
          goto LABEL_86;
        }
        ++dword_1800C43B0;
LABEL_81:
        Heap[1] = *((_OWORD *)a1 + 2);
        *((_QWORD *)Heap + 4) = *((_QWORD *)a1 + 74);
        v52 = qword_1800C43A0;
        if ( *(__int64 **)(qword_1800C43A0 + 8) != &qword_1800C43A0 )
          goto LABEL_82;
        *(_QWORD *)Heap = qword_1800C43A0;
        *((_QWORD *)Heap + 1) = &qword_1800C43A0;
        *(_QWORD *)(v52 + 8) = Heap;
        qword_1800C43A0 = (__int64)Heap;
        goto LABEL_84;
      }
      Heap = (_OWORD *)qword_1800C43A8;
      if ( *(__int64 **)qword_1800C43A8 == &qword_1800C43A0 )
      {
        v50 = *(_QWORD **)(qword_1800C43A8 + 8);
        if ( *v50 == qword_1800C43A8 )
        {
          qword_1800C43A8 = *(_QWORD *)(qword_1800C43A8 + 8);
          *v50 = &qword_1800C43A0;
          NtDeleteWnfStateName(Heap + 2);
          goto LABEL_81;
        }
      }
LABEL_82:
      __fastfail(3u);
    }
  }
LABEL_86:
  if ( *((_DWORD *)a1 + 100) == 1 && (*((_DWORD *)a1 + 104) || *((_DWORD *)a1 + 105)) )
  {
    v55 = *((_QWORD *)a1 + 52);
    v58 = 0;
    RtlWaitForWnfMetaNotification(v55, 8, 5000, 1000, &v58);
    NtDeleteWnfStateName((char *)a1 + 416);
  }
  BipCoalesceContextAcquireLockExclusive(*((struct _BI_COALESCING_CONTEXT **)a1 + 45));
  v56 = *((_QWORD *)a1 + 45);
  v57 = ~(1 << *(_DWORD *)(v56 - 8));
  *(_DWORD *)(v56 - 4) = 0;
  *v42 &= v57;
  RtlReleaseSRWLockExclusive(v56 - 16);
  *v44 &= v57;
}

```

## disassembly

```asm
0x180058b20  mov     [rsp-8+arg_18], rbx
0x180058b25  push    rbp
0x180058b26  push    rsi
0x180058b27  push    rdi
0x180058b28  push    r12
0x180058b2a  push    r13
0x180058b2c  lea     rbp, [rsp-37h]
0x180058b31  sub     rsp, 0A0h
0x180058b38  mov     rax, cs:__security_cookie
0x180058b3f  xor     rax, rsp
0x180058b42  mov     [rbp+57h+var_30], rax
0x180058b46  mov     eax, cs:dword_1800C3098
0x180058b4c  lea     rbx, _TraceLoggingMetadataEnd
0x180058b53  xor     r12d, r12d
0x180058b56  lea     rdi, _TraceLoggingMetadata
0x180058b5d  mov     rsi, rcx
0x180058b60  mov     r13d, 1
0x180058b66  cmp     eax, 5
0x180058b69  jbe     loc_180058C2D
0x180058b6f  mov     rcx, cs:qword_1800C30B0
0x180058b76  mov     rax, cs:qword_1800C30A8
0x180058b7d  test    al, 2
0x180058b7f  jz      loc_180058C2D
0x180058b85  mov     rax, rcx
0x180058b88  and     eax, 2
0x180058b8b  cmp     rax, rcx
0x180058b8e  jnz     loc_180058C2D
0x180058b94  mov     [rbp+57h+var_38], 10h
0x180058b9c  lea     rax, [rsi+20h]
0x180058ba0  mov     [rbp+57h+var_40], rax
0x180058ba4  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180058ba8  lea     rax, qword_1800A1850
0x180058baf  mov     [rbp+57h+var_48], r13
0x180058bb3  mov     [rbp+57h+var_50], rax
0x180058bb7  xor     r9d, r9d; RelatedActivityId
0x180058bba  movzx   eax, cs:word_1800B34A7
0x180058bc1  xor     r8d, r8d; ActivityId
0x180058bc4  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180058bc7  mov     rax, cs:off_1800C30A0
0x180058bce  mov     [rbp+57h+var_70.Ptr], rax
0x180058bd2  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180058bd9  mov     [rbp+57h+EventDescriptor.Keyword], 2
0x180058be1  movzx   eax, word ptr [rax]
0x180058be4  mov     [rbp+57h+var_70.Size], eax
0x180058be7  lea     rax, byte_1800B34B1
0x180058bee  mov     [rbp+57h+var_60], rax
0x180058bf2  mov     rax, rbx
0x180058bf5  sub     eax, edi
0x180058bf7  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x180058bfe  mov     [rbp+57h+var_58], 25h ; '%'
0x180058c05  mov     [rbp+57h+var_54], r13d
0x180058c09  mov     [rbp+57h+var_90], eax
0x180058c0c  mov     eax, [rbp+57h+var_90]
0x180058c0f  mov     rcx, cs:RegHandle; RegHandle
0x180058c16  lea     rax, [rbp+57h+var_70]
0x180058c1a  mov     [rsp+0C0h+UserData], rax; UserData
0x180058c1f  mov     [rsp+0C0h+UserDataCount], 4; UserDataCount
0x180058c27  call    cs:__imp_EventWriteTransfer
0x180058c2d  mov     [rsp+0C0h+arg_8], r14
0x180058c35  xor     edx, edx; unsigned __int8
0x180058c37  mov     rcx, rsi; struct _BI_WORK_ITEM *
0x180058c3a  mov     [rsp+0C0h+arg_10], r15
0x180058c42  call    ?BipSystemStateCheckSetWorkItemNetworkRequest@@YAXPEAU_BI_WORK_ITEM@@E@Z; BipSystemStateCheckSetWorkItemNetworkRequest(_BI_WORK_ITEM *,uchar)
0x180058c47  call    BipAcquireGlobalLock
0x180058c4c  lea     rcx, [rsi+0F0h]
0x180058c53  mov     rax, [rcx]
0x180058c56  test    rax, rax
0x180058c59  jz      short loc_180058C8B
0x180058c5b  mov     rax, [rcx+8]
0x180058c5f  test    rax, rax
0x180058c62  jz      short loc_180058C8B
0x180058c64  mov     rax, [rcx]
0x180058c67  cmp     [rax+8], rcx
0x180058c6b  jnz     loc_18005925E
0x180058c71  mov     rdx, [rcx+8]
0x180058c75  cmp     [rdx], rcx
0x180058c78  jnz     loc_18005925E
0x180058c7e  mov     [rdx], rax
0x180058c81  xorps   xmm0, xmm0
0x180058c84  mov     [rax+8], rdx
0x180058c88  movups  xmmword ptr [rcx], xmm0
0x180058c8b  lea     rcx, [rsi+100h]
0x180058c92  mov     rax, [rcx]
0x180058c95  test    rax, rax
0x180058c98  jz      short loc_180058CCA
0x180058c9a  mov     rax, [rcx+8]
0x180058c9e  test    rax, rax
0x180058ca1  jz      short loc_180058CCA
0x180058ca3  mov     rax, [rcx]
0x180058ca6  cmp     [rax+8], rcx
0x180058caa  jnz     loc_18005925E
0x180058cb0  mov     rdx, [rcx+8]
0x180058cb4  cmp     [rdx], rcx
0x180058cb7  jnz     loc_18005925E
0x180058cbd  mov     [rdx], rax
0x180058cc0  xorps   xmm0, xmm0
0x180058cc3  mov     [rax+8], rdx
0x180058cc7  movups  xmmword ptr [rcx], xmm0
0x180058cca  lea     rcx, [rsi+120h]
0x180058cd1  mov     rax, [rcx]
0x180058cd4  test    rax, rax
0x180058cd7  jz      short loc_180058D09
0x180058cd9  mov     rax, [rcx+8]
0x180058cdd  test    rax, rax
0x180058ce0  jz      short loc_180058D09
0x180058ce2  mov     rax, [rcx]
0x180058ce5  cmp     [rax+8], rcx
0x180058ce9  jnz     loc_18005925E
0x180058cef  mov     rdx, [rcx+8]
0x180058cf3  cmp     [rdx], rcx
0x180058cf6  jnz     loc_18005925E
0x180058cfc  mov     [rdx], rax
0x180058cff  xorps   xmm0, xmm0
0x180058d02  mov     [rax+8], rdx
0x180058d06  movups  xmmword ptr [rcx], xmm0
0x180058d09  mov     ecx, [rsi+190h]
0x180058d0f  mov     edx, ecx
0x180058d11  mov     r14d, 4
0x180058d17  mov     r15d, 8
0x180058d1d  test    ecx, ecx
0x180058d1f  jz      short loc_180058D33
0x180058d21  sub     edx, r13d
0x180058d24  jz      loc_180059079
0x180058d2a  cmp     edx, r13d
0x180058d2d  jnz     loc_180059079
0x180058d33  mov     r14, [rsi+50h]
0x180058d37  test    r14, r14
0x180058d3a  jz      loc_180059073
0x180058d40  mov     edx, ecx
0x180058d42  test    ecx, ecx
0x180058d44  jz      short loc_180058D63
0x180058d46  sub     edx, r13d
0x180058d49  jz      short loc_180058DA6
0x180058d4b  cmp     edx, r13d
0x180058d4e  jnz     short loc_180058DA6
0x180058d50  test    ecx, ecx
0x180058d52  jz      short loc_180058D63
0x180058d54  sub     ecx, r13d
0x180058d57  jz      short loc_180058D5E
0x180058d59  cmp     ecx, r13d
0x180058d5c  jz      short loc_180058D63
0x180058d5e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180058d63  mov     rcx, [rsi+58h]; P
0x180058d67  test    rcx, rcx
0x180058d6a  jz      short loc_180058DA6
0x180058d6c  mov     [rsi+58h], r12
0x180058d70  lea     rax, [rsi+0B0h]
0x180058d77  dec     dword ptr [rcx+38h]
0x180058d7a  mov     r8, [rax]
0x180058d7d  cmp     [r8+8], rax
0x180058d81  jnz     loc_18005925E
0x180058d87  mov     rdx, [rax+8]
0x180058d8b  cmp     [rdx], rax
0x180058d8e  jnz     loc_18005925E
0x180058d94  mov     [rdx], r8
0x180058d97  xorps   xmm0, xmm0
0x180058d9a  mov     [r8+8], rdx
0x180058d9e  movups  xmmword ptr [rax], xmm0
0x180058da1  call    BipConditionallyDeletePackageApplication
0x180058da6  lea     rax, [rsi+0A0h]
0x180058dad  mov     rdx, [rax]
0x180058db0  cmp     [rdx+8], rax
0x180058db4  jnz     loc_18005925E
0x180058dba  mov     rcx, [rax+8]
0x180058dbe  cmp     [rcx], rax
0x180058dc1  jnz     loc_18005925E
0x180058dc7  mov     [rcx], rdx
0x180058dca  xorps   xmm0, xmm0
0x180058dcd  mov     [rdx+8], rcx
0x180058dd1  movups  xmmword ptr [rax], xmm0
0x180058dd4  lea     rax, [r14+20h]
0x180058dd8  mov     [rsi+50h], r12
0x180058ddc  cmp     [rax], rax
0x180058ddf  jnz     loc_180059073
0x180058de5  lea     rax, [r14+40h]
0x180058de9  cmp     [rax], rax
0x180058dec  jnz     loc_180059073
0x180058df2  cmp     [r14+23Ch], r12d
0x180058df9  jnz     loc_180059073
0x180058dff  cmp     dword ptr [r14+240h], 0FFFFFFFFh
0x180058e07  jnz     loc_180059073
0x180058e0d  lea     rax, [r14+60h]
0x180058e11  cmp     [rax], rax
0x180058e14  jnz     loc_180059073
0x180058e1a  lea     rax, [r14+30h]
0x180058e1e  cmp     [rax], rax
0x180058e21  jnz     loc_180059073
0x180058e27  test    byte ptr [r14+25Ch], 2
0x180058e2f  jnz     loc_180059073
0x180058e35  mov     eax, cs:dword_1800C3098
0x180058e3b  cmp     eax, 5
0x180058e3e  jbe     loc_180058F23
0x180058e44  mov     rcx, cs:qword_1800C30B0
0x180058e4b  mov     rax, cs:qword_1800C30A8
0x180058e52  test    al, 2
0x180058e54  jz      loc_180058F23
0x180058e5a  mov     rax, rcx
0x180058e5d  and     eax, 2
0x180058e60  cmp     rax, rcx
0x180058e63  jnz     loc_180058F23
0x180058e69  lea     rcx, [r14+0A0h]
0x180058e70  test    rcx, rcx
0x180058e73  jz      short loc_180058E95
0x180058e75  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180058e7c  nop     dword ptr [rax+00h]
0x180058e80  cmp     [rcx+rax*2+2], r12w
0x180058e86  lea     rax, [rax+1]
0x180058e8a  jnz     short loc_180058E80
0x180058e8c  lea     eax, ds:2[rax*2]
0x180058e93  jmp     short loc_180058EA1
0x180058e95  lea     rcx, qword_1800A1670
0x180058e9c  mov     eax, 2
0x180058ea1  mov     dword ptr [rbp+57h+var_48], eax
0x180058ea4  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180058ea8  movzx   eax, cs:word_1800AF5D1
0x180058eaf  sub     ebx, edi
0x180058eb1  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180058eb4  xor     r9d, r9d; RelatedActivityId
0x180058eb7  mov     rax, cs:off_1800C30A0
0x180058ebe  xor     r8d, r8d; ActivityId
0x180058ec1  mov     [rbp+57h+var_70.Ptr], rax
0x180058ec5  mov     [rbp+57h+var_50], rcx
0x180058ec9  mov     dword ptr [rbp+57h+var_48+4], r12d
0x180058ecd  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180058ed4  mov     [rbp+57h+EventDescriptor.Keyword], 2
0x180058edc  movzx   eax, word ptr [rax]
0x180058edf  mov     [rbp+57h+var_70.Size], eax
0x180058ee2  lea     rax, byte_1800AF5DB
0x180058ee9  mov     [rbp+57h+var_60], rax
0x180058eed  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x180058ef4  mov     [rbp+57h+var_58], 24h ; '$'
0x180058efb  mov     [rbp+57h+var_54], r13d
0x180058eff  mov     [rbp+57h+var_90], ebx
0x180058f02  mov     eax, [rbp+57h+var_90]
0x180058f05  mov     rcx, cs:RegHandle; RegHandle
0x180058f0c  lea     rax, [rbp+57h+var_70]
0x180058f10  mov     [rsp+0C0h+UserData], rax; UserData
0x180058f15  mov     [rsp+0C0h+UserDataCount], 3; UserDataCount
0x180058f1d  call    cs:__imp_EventWriteTransfer
0x180058f23  mov     rcx, cs:qword_1800C4380
0x180058f2a  xor     r8d, r8d
0x180058f2d  mov     rdx, r14
0x180058f30  call    cs:__imp_RtlRemoveEntryHashTable
0x180058f36  lea     r12, [r14+80h]
0x180058f3d  mov     rbx, [r12]
0x180058f41  cmp     rbx, r12
0x180058f44  jz      short loc_180058F90
0x180058f46  nop     word ptr [rax+rax+00000000h]
0x180058f50  mov     rdi, rbx
0x180058f53  mov     r15, rbx
0x180058f56  mov     rbx, [rbx]
0x180058f59  mov     r8, [rdi+30h]; P
0x180058f5d  test    r8, r8
0x180058f60  jz      short loc_180058F79
0x180058f62  mov     rcx, cs:BipHeap; HeapHandle
0x180058f69  xor     edx, edx; Flags
0x180058f6b  call    cs:__imp_RtlFreeHeap
0x180058f71  mov     qword ptr [rdi+30h], 0
0x180058f79  mov     rcx, cs:BipHeap; HeapHandle
0x180058f80  mov     r8, r15; P
0x180058f83  xor     edx, edx; Flags
0x180058f85  call    cs:__imp_RtlFreeHeap
0x180058f8b  cmp     rbx, r12
0x180058f8e  jnz     short loc_180058F50
0x180058f90  mov     rdi, cs:qword_1800C45C0
0x180058f97  mov     ebx, r13d
0x180058f9a  mov     rax, gs:58h
0x180058fa3  mov     r15d, 4
0x180058fa9  mov     ecx, [rdi+8]
0x180058fac  shl     ebx, cl
0x180058fae  mov     ecx, cs:_tls_index
0x180058fb4  mov     r12, [rax+rcx*8]
0x180058fb8  add     r15, r12
0x180058fbb  cmp     [r15], ebx
0x180058fbe  jb      short loc_180058FD2
0x180058fc0  call    cs:__imp_IsDebuggerPresent
0x180058fc6  test    eax, eax
0x180058fc8  jz      short loc_180058FD2
0x180058fca  mov     rcx, rdi; struct _BI_LOCK *
0x180058fcd  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x180058fd2  mov     rcx, rdi
0x180058fd5  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180058fdb  call    cs:__imp_GetCurrentThreadId
0x180058fe1  or      [r15], ebx
0x180058fe4  mov     [rdi+0Ch], eax
0x180058fe7  mov     eax, 8
0x180058fec  add     r12, rax
0x180058fef  movzx   eax, byte ptr [rdi+0B0h]
0x180058ff6  or      [r12], ebx
0x180058ffa  test    al, 4
0x180058ffc  jnz     short loc_180059022
0x180058ffe  cmp     word ptr [rdi+20h], 0
0x180059003  jz      short loc_180059022
0x180059005  cmp     word ptr [rdi+22h], 0
0x18005900a  jz      short loc_180059022
0x18005900c  cmp     word ptr [rdi+24h], 64h ; 'd'
0x180059011  jnb     short loc_180059022
0x180059013  test    al, 40h
0x180059015  jnz     short loc_180059022
0x180059017  mov     rdx, r14
  ... truncated ...
```
